# Template: Bug Report

> **How to use:** Coaching the team to this standard is one of a new QA Lead's easiest early wins — see [04 — Bug Lifecycle & Triage](../04-bug-lifecycle-and-triage.md). A bug a developer can fix without a meeting saves hours. Severity is the *technical* impact; priority is set at triage.

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

# Bug: [SPECIFIC, SEARCHABLE TITLE]

**Reporter:** [NAME]
**Date:** [YYYY-MM-DD]
**Severity (proposed):** `S1` | `S2` | `S3` | `S4`
**Frequency:** `Always` | `Intermittent (X/10)` | `Once`
**Environment:** [browser / OS / app version / env]

---

## Steps to Reproduce
1. [from a known starting state]
2. [ ]
3. [ ]

## Expected Result
[what should happen]

## Actual Result
[what actually happens]

## Evidence
- [screenshot / video / log snippet / request-response]

## Additional Context
- [feature flags, account type, data state, related tickets]

---

## ─── FILLED EXAMPLE ───────────────────────────────────────────────

---

# Bug: Checkout returns 500 when applying an expired coupon

**Reporter:** Dara
**Date:** 2026-06-10
**Severity (proposed):** S2
**Frequency:** Always
**Environment:** Chrome 125 / macOS / staging / build 2026.06.10-rc2

## Steps to Reproduce
1. Add any item to cart and go to checkout.
2. Enter coupon code `SUMMER2024` (expired 2024-09-01).
3. Click **Apply**.

## Expected Result
A friendly inline error: "This coupon has expired."

## Actual Result
Page shows a 500 error; cart becomes inaccessible until refresh.

## Evidence
- Screenshot of 500 page (attached)
- Log: `NullPointerException at CouponService.validate() line 88`

## Additional Context
- Only expired coupons trigger it; invalid (never-existed) codes error correctly.
- Likely missing null-check on `coupon.expiryDate`.

---

*Template for the [QA Leadership Playbook](../README.md)*
