# Template: Test Plan (Per Feature / Release)

> **How to use:** A QA engineer writes one of these per feature or release, derived from the team [Test Strategy](../03-test-strategy.md). The strategy says *how we test in general*; this says *how we test THIS thing*. Keep it lean — link to the strategy instead of repeating it.

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

# Test Plan — [FEATURE / RELEASE NAME]

**Author:** [NAME]
**Date:** [YYYY-MM-DD]
**Related:** [ticket / PRD link]
**Strategy ref:** [link to team test strategy]

---

## 1. Scope
**In scope:** [what we test]
**Out of scope:** [what we deliberately don't]

## 2. Risk Assessment
| Area | Risk (H/M/L) | Why |
|:-----|:------------:|:----|
| [area] | [ ] | [reason] |

## 3. Test Approach
| Level | Owner | Notes |
|:------|:------|:------|
| Unit | Dev | [ ] |
| Integration | Dev/QA | [ ] |
| E2E | QA | [ ] |
| Exploratory | QA | [ ] |
| Manual | QA | [ ] |

## 4. Environment & Data
- **Environment:** [ ]
- **Test data:** [how seeded]

## 5. Entry Criteria (ready to test)
- [ ] Acceptance criteria written
- [ ] Deployed to [env]
- [ ] Test data available

## 6. Exit Criteria (ready to ship)
- [ ] Critical/high cases pass
- [ ] 0 open S1/S2
- [ ] Regression green
- [ ] PO acceptance

## 7. Test Cases
| ID | Scenario | Type | Priority | Status |
|:---|:---------|:-----|:--------:|:------:|
| TC-1 | [scenario] | [pos/neg/edge] | [ ] | [ ] |

## 8. Risks & Assumptions
- [ ]

---

## ─── FILLED EXAMPLE (excerpt) ─────────────────────────────────────

---

**Feature:** Coupon codes at checkout
**In scope:** apply/remove coupon, expired/invalid handling, stacking rules.
**Out of scope:** coupon admin creation (covered separately).

**Risk:** Checkout = 🔴 High (revenue path). Expired-coupon handling = 🔴 (current 500 bug).

| ID | Scenario | Type | Priority | Status |
|:---|:---------|:-----|:--------:|:------:|
| TC-1 | Valid coupon applies discount | Positive | High | Pass |
| TC-2 | Expired coupon shows friendly error | Negative | High | Pass |
| TC-3 | Two coupons can't stack | Edge | Med | Pass |

**Exit:** all High pass, 0 S1/S2 — ✅ ready.

---

*Template for the [QA Leadership Playbook](../README.md)*
