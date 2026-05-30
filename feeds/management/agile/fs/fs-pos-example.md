# FS: POS Checkout & Split Payment (Example)

> A worked example of the [Functional Spec Procedure](fs-document-procedure.md), filled in for a Point-of-Sale (POS) feature. Use it as a reference for how a real FS reads. The names and numbers are illustrative.

| Field | Value |
|-------|-------|
| Author (PO) | Sophea |
| Date | 2026-06-02 |
| Status | Approved |
| Target sprint | Sprint 25 (Jun 16 – Jun 27) |
| Reviewers | PM Dara, Dev Visal, QA Chenda |

## 1. Summary

Cashiers need to ring up a sale, accept payment, and print a receipt at the counter. Today they can only take a single payment method per sale, which forces awkward workarounds when a customer wants to pay part cash and part card. This FS defines the **checkout flow** and adds **split payment** (more than one payment method on one sale) so the cashier can complete the sale in a single transaction.

## 2. Background / Problem

The current POS accepts exactly one payment per sale. In stores, customers regularly want to split — pay $20 in cash and the remainder on card, or use a gift card plus cash. Cashiers handle this today by voiding and re-ringing, which is slow, error-prone, and produces two receipts that accounting can't easily reconcile. We lose time at the counter and create reconciliation work at end of day.

## 3. Goals & Non-Goals

**Goals:**
- A cashier can build a sale (add/remove items, see the running total).
- A cashier can take **one or more** payments on a single sale until the balance is zero.
- The system prints/issues one receipt showing each payment.
- The sale is recorded as a single transaction for reconciliation.

**Non-Goals:**
- Refunds and returns (separate FS).
- Inventory deduction logic (already exists; this FS only references it).
- Loyalty points / discounts (future sprint).
- Hardware driver work for the card reader (assumed already integrated).

## 4. Users / Personas

- **Cashier** — rings up sales fast at the counter; wants the fewest taps to finish a sale and clear, immediate feedback when something is wrong.
- **Store Manager** — reviews the day's sales; wants every sale (including split-paid ones) to reconcile cleanly to one transaction record.

## 5. User Stories

- As a **cashier**, I want to add items to a sale and see the running total so that I can tell the customer what they owe.
- As a **cashier**, I want to take a partial payment and see the remaining balance so that I can collect the rest by another method.
- As a **cashier**, I want the sale to close automatically when the balance reaches zero so that I don't accidentally overcharge.
- As a **store manager**, I want each split-paid sale recorded as one transaction so that end-of-day reconciliation is clean.

## 6. Functional Requirements

- **FR-1:** The cashier can add and remove line items; the sale shows a running subtotal, tax, and total.
- **FR-2:** The cashier can record a payment of a chosen method (cash, card, gift card) for an amount up to the remaining balance.
- **FR-3:** After each payment, the system shows the **remaining balance** and the list of payments taken so far.
- **FR-4:** The sale **cannot be over-paid**: a payment amount may not exceed the remaining balance (except cash, where change due is calculated and shown).
- **FR-5:** When the remaining balance reaches zero, the sale is marked **Complete** and no further items or payments can be added.
- **FR-6:** On completion, the system issues **one receipt** listing each payment method and amount, and records the sale as a **single transaction** with its payment breakdown.
- **FR-7:** The cashier can **cancel** an incomplete sale; any payments already taken in that sale are voided and logged.

## 7. Acceptance Criteria

- **FR-1:** Given an open sale, When the cashier adds an item priced $5.00, Then the running total increases by $5.00 plus applicable tax.
- **FR-2:** Given a sale with a $50.00 balance, When the cashier records a $20.00 cash payment, Then the payment is accepted and recorded.
- **FR-3:** Given the $20.00 payment above, When it is recorded, Then the screen shows "Remaining: $30.00" and lists "Cash $20.00".
- **FR-4 (card):** Given a $30.00 remaining balance, When the cashier tries to charge $40.00 to a card, Then the system rejects it with "Amount exceeds remaining balance".
- **FR-4 (cash):** Given a $30.00 remaining balance, When the cashier takes $50.00 cash, Then the system accepts it, marks the sale paid, and shows "Change due: $20.00".
- **FR-5:** Given a sale whose remaining balance has reached $0.00, When the cashier tries to add another item, Then the action is blocked and the sale shows "Complete".
- **FR-6:** Given a sale paid by $20.00 cash and $30.00 card, When it completes, Then one receipt lists both payments and one transaction record stores the $50.00 total with a 2-line payment breakdown.
- **FR-7:** Given an incomplete sale with one $20.00 payment taken, When the cashier cancels it, Then the $20.00 is voided, a void entry is logged, and the sale does not appear in completed sales.

## 8. Non-Functional Requirements

- **Performance:** Adding an item and recording a payment each reflect on screen in under 500 ms on the store's standard terminal.
- **Reliability:** If the terminal loses power mid-sale, on restart the cashier sees the in-progress sale recovered (payments already taken are not lost).
- **Auditability:** Every payment and void is logged with cashier ID, timestamp, amount, and method.
- **Localization:** Currency and tax follow the store's configured locale.

## 9. Out of Scope

- Refunds/returns, loyalty/discounts, multi-currency within one sale, and card-reader hardware integration are not part of this FS.

## 10. Dependencies & Assumptions

- The card reader is already integrated and returns success/failure synchronously.
- The tax engine and inventory deduction services exist and are called, not built here.
- Assumes a single cashier per terminal per sale (no concurrent edits to the same sale).

## 11. Open Questions

- Should a gift card that exceeds the balance leave a remaining gift-card value, or forfeit it? — owner: Sophea (PO), due: 2026-06-06.
- Is a manager override required to cancel a sale with payments already taken? — owner: Dara (PM), due: 2026-06-06.
