# FS Module 4 (Detailed): Sales Channels & Orders — Build-Ready Spec

> Deep companion to [Module 4 — Channels & Orders](04-channels-orders.md), taken to full build-ready depth (Stanford-style FSD): use cases, screen mock-up, field-level specifications, validation/error rules, and control behaviors. This is the **gold-standard depth** a module reaches when it enters a build sprint; the functional module stays the readable overview.

## Document Control

| Field | Value |
|-------|-------|
| Status | `<Draft / In Review / Approved>` |
| Version | `<0.1>` |
| Author (PO) | Sophea |
| Reviewers | PM Dara, Dev Visal, QA Chenda |
| Last updated | `<YYYY-MM-DD>` |
| Parent FS | [04 — Channels & Orders](04-channels-orders.md) |

---

## 1. Purpose / Description

This detailed spec covers the **Order Capture screen** and the **order confirmation flow** — the screen a Sales agent uses dozens of times a day to turn a TikTok/Facebook conversation into a tracked order. It exists because order capture is the highest-volume, highest-risk human action in the system: a slow or error-prone screen loses sales and creates oversell. The detail here (fields, validations, button behavior) makes the screen unambiguous to build and test.

Traces to parent requirements **OR-1, OR-3, OR-5, OR-6, OR-7** and user stories in [Module 4](04-channels-orders.md#user-stories).

---

## 2. Use Cases

### UC-4.1 — Capture and confirm a new order

| Element | Detail |
|---------|--------|
| **Primary actor** | Sales agent |
| **Stakeholders & interest** | Customer (wants their order placed correctly); Owner (wants no lost sale, no oversell); Fulfillment (needs accurate address & items) |
| **Trigger** | A customer expresses intent to buy via TikTok/Facebook chat, comment, or live |
| **Pre-conditions** | Agent is logged in with the Sales role; products exist in the catalog |
| **Post-conditions (success)** | An Order exists in Confirmed state; stock is reserved for stocked lines; a dropship line has raised a purchase trigger |
| **Main success scenario** | 1. Agent opens **New Order**. 2. Agent enters customer phone/handle; system shows history if found. 3. Agent adds line items (variant + qty), seeing the running total. 4. Agent optionally applies a per-line discount. 5. Agent selects payment method and delivery address. 6. Agent clicks **Confirm Order**. 7. System validates stock, reserves stocked lines, flags dropship lines, and saves the order as Confirmed. |
| **Extensions** | 2a. Customer not found → agent fills name/address manually, a new customer is created on save. 3a. Variant out of stock (stocked) → line shows "insufficient stock", Confirm blocked for that line. 6a. Another agent reserved the last unit first → Confirm fails with "insufficient stock"; agent adjusts qty or offers alternative. 6b. Duplicate suspected (same customer+items in last few minutes) → warning shown; agent confirms or cancels. |
| **Priority** | High |
| **Special requirements** | Screen usable on mobile (NFR-13); capture ≤ 30s (NFR-14) |
| **Open questions** | Should manager approval be required for discounts beyond a threshold? — owner: Dara (PM) |

### UC-4.2 — Import a TikTok Shop order

| Element | Detail |
|---------|--------|
| **Primary actor** | System (TikTok integration), reviewed by Sales agent |
| **Trigger** | A new paid order arrives via the TikTok Shop API |
| **Pre-conditions** | TikTok integration connected; products mapped to catalog SKUs |
| **Post-conditions** | Order created (Confirmed) with line items matched to catalog; flagged for agent review if any SKU is unmatched |
| **Main success scenario** | 1. API pushes a new order. 2. System matches each line to a catalog SKU. 3. System creates the order and reserves stock. 4. Agent sees it in the order list, no typing required. |
| **Extensions** | 2a. SKU unmatched → order held in "needs review"; agent maps the product manually. 1a. API unavailable → no import; agent may capture manually (UC-4.1), de-duplicated later. |
| **Priority** | Medium (Post-MVP) |

---

## 3. Mock-up — Order Capture screen

*(Low-fidelity; final visual design in the design tool. Call-outs ① etc. map to the field table in §4.)*

```
┌───────────────────────────────────────────────────────┐
│  New Order                       ① Channel: [Facebook ▾]│
├───────────────────────────────────────────────────────┤
│  ② Customer phone/handle: [ @dara________ ] 🔎          │
│     ⓘ Returning · 4 orders · LTV 180                    │
│  ③ Name: [ Dara ]                                       │
│  ④ Delivery address: [ ............................... ]│
├───────────────────────────────────────────────────────┤
│  Items                                    [⑤ + Add item]│
│   ⑥ Red Tee / L    ⑦x[2]   25  ⑧(−3)  = 44   [remove]   │
│   ⑥ LED Lamp       ⑦x[1]   13         = 13   [remove]   │
│                                   Subtotal:    57        │
│                                   Tax:          2        │
│                                   ⑨ TOTAL:     59        │
├───────────────────────────────────────────────────────┤
│  ⑩ Payment method: [ COD ▾ ]                            │
│  ⑪ Notes: [ deliver after 5pm ]                         │
│                                                         │
│        [⑫ Save Draft ]            [⑬ Confirm Order ]    │
└───────────────────────────────────────────────────────┘
```

---

## 4. Field-Level Specifications

### Form elements

| Call-out | Field label | UI control | Mand? | Editable | Data type | Value set | Default | Data example | Data source |
|----------|-------------|-----------|-------|----------|-----------|-----------|---------|--------------|-------------|
| ① | Channel | dropdown | Yes | Yes | enum | TikTok / Facebook / Manual / Live | Manual | Facebook | system |
| ② | Customer phone/handle | textbox + search | Yes | Yes | alphanumeric | — | empty | @dara | user entry → Customer lookup |
| ③ | Name | textbox | Yes | Yes | text | — | from lookup | Dara | user / Customer |
| ④ | Delivery address | textarea | Yes* | Yes | text | — | from lookup | St 120, PP | user / Customer |
| ⑤ | Add item | button | — | — | — | — | — | — | — |
| ⑥ | Item (variant) | searchable select | Yes | Yes | ref→Variant | catalog variants | empty | Red Tee / L | Catalog |
| ⑦ | Qty | number stepper | Yes | Yes | integer ≥1 | — | 1 | 2 | user entry |
| ⑧ | Line discount | number | No | Yes | money ≥0 | — | 0 | 3 | user entry |
| ⑨ | Total | label (read-only) | — | No | money | — | computed | 59 | computed |
| ⑩ | Payment method | dropdown | Yes | Yes | enum | COD / Bank-ABA / Wallet / Prepaid | COD | COD | system |
| ⑪ | Notes | textbox | No | Yes | text | — | empty | deliver after 5pm | user entry |

\* Address is mandatory before **Confirm** for delivery, but optional while **Save Draft**.

### Form business rules, validations & errors

| Field | Validation / business rule | Error message | Data dependency | Notes |
|-------|----------------------------|---------------|-----------------|-------|
| ② Phone/handle | Required; on entry, search existing customers | "Enter a customer phone or handle" | Customer records | Match shows history (CU-2) |
| ④ Address | Required before Confirm (not Draft) | "Delivery address is required to confirm" | — | — |
| ⑦ Qty | Integer ≥ 1; for **stocked** variants, qty ≤ available | "Only N in stock" | Inventory available_qty (IN-3) | Dropship variants have no cap |
| ⑧ Line discount | ≥ 0 and may not push the line below its margin floor | "Discount exceeds allowed margin" | Landed cost (LC), Promotions guardrail (PRO-4) | Records discount for margin (OR-7) |
| ⑩ Payment method | Required | "Select a payment method" | — | Sets payment intent (Module 6) |
| Order (on Confirm) | At least one line item; total > 0 | "Add at least one item" | — | — |

### Buttons, links & icons

| Control | OnClick | Visible | Enabled vs disabled | Navigate to | Validation | Dependencies |
|---------|---------|---------|---------------------|-------------|------------|--------------|
| 🔎 (lookup, ②) | Search customers by phone/handle; show history panel if found | Always | Enabled when ② non-empty | — | — | — |
| ⑤ Add item | Add a new blank line row | Always | Always | — | — | — |
| remove (per line) | Remove that line; recompute totals | Per line | Always | — | — | — |
| ⑫ Save Draft | Save the order as **Draft** (no stock reserved) | Always | Always | Order list | Customer handle present | — |
| ⑬ Confirm Order | Validate all fields + stock; reserve stocked lines; flag dropship; save as **Confirmed** | Always | Disabled until ≥1 item, customer, address, payment method present | Order detail | Stock check (OR-6); margin check (⑧) | On stock fail, blocks and shows per-line error |

---

## 5. Non-Functional (screen-specific)

- Capturing a typical order: **≤ 30s** (NFR-14); fully usable on a **phone** (NFR-13).
- Running total and stock check reflect in **< 1s** (NFR-1).
- Every blocked action shows a **plain-language reason** (NFR-15) — see error table above.

---

## 6. Open Issues

| ID | Issue | Raised by | Status |
|----|-------|-----------|--------|
| OI-1 | Discount threshold needing manager approval — value? | Dara (PM) | Open |
| OI-2 | Live-claim capture: separate fast screen vs this form? (see [Module 13](13-live-selling.md)) | Sophea (PO) | Open |

---

## 7. Approval

Internal working agreement, not a legal contract.

| Role | Name | Status (Reviewed / Approved) | Date |
|------|------|------------------------------|------|
| Product Owner (PO) | Sophea | `<>` | `<YYYY-MM-DD>` |
| Project Manager (PM) | Dara | `<>` | `<YYYY-MM-DD>` |
| Dev Lead | Visal | `<>` | `<YYYY-MM-DD>` |
| QA | Chenda | `<>` | `<YYYY-MM-DD>` |

## 8. Change Log

| Version | Date | Author | Change |
|---------|------|--------|--------|
| 0.1 | `<YYYY-MM-DD>` | Sophea | Initial detailed spec |
