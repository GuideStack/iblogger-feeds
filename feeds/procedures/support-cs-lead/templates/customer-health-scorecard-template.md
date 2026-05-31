# Template: Customer Health Scorecard

> **How to use:** A health score is an early-warning system — a single composite signal per account that triggers proactive action *before* a customer is in crisis. Weight the dimensions to your business, roll up to Green / Yellow / Red, and make each risk level **trigger a play**. A scorecard nobody acts on is theater. See [05 — Retention & Customer Success](../05-retention-and-customer-success.md).

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

# Customer Health Scorecard — [ACCOUNT NAME]

**Owner (CSM):** [ ] · **Segment:** [High / Mid / Tech-touch] · **Renewal date:** [YYYY-MM-DD] · **ARR:** [ ]

## Dimensions

| Dimension | Weight | Signal | Score (1–5) | Weighted |
|:----------|:------:|:-------|:-----------:|:--------:|
| Product usage | [ ] | [login freq, core-feature use, active seats] | [ ] | [ ] |
| Engagement | [ ] | [responds to outreach, attends QBRs, has champion] | [ ] | [ ] |
| Support experience | [ ] | [ticket volume, CSAT, open escalations] | [ ] | [ ] |
| Sentiment | [ ] | [NPS, survey tone, relationship feel] | [ ] | [ ] |
| Account fit / stakeholder | [ ] | [right use case, champion still present] | [ ] | [ ] |
| **TOTAL** | 100% | | | **[ ]** |

## Health Level & Triggers

| Level | Score range | Meaning | Trigger / play |
|:------|:-----------:|:--------|:---------------|
| 🟢 Green | [ ] | Healthy; on track | Maintain; watch for expansion |
| 🟡 Yellow | [ ] | Drifting; early risk | Proactive check-in within [N] days |
| 🔴 Red | [ ] | At risk of churn | Save-play: owner + plan within [N] days |

## Notes / Risk Factors
- [ ]

## Action Log
| Date | Action | Owner | Result |
|:-----|:-------|:------|:-------|
| [ ] | [ ] | [ ] | [ ] |

---

## ─── FILLED EXAMPLE ───────────────────────────────────────────────

---

# Customer Health Scorecard — Northwind Logistics

**Owner (CSM):** Dara · **Segment:** High-touch (enterprise) · **Renewal date:** 2026-09-30 · **ARR:** $84k

## Dimensions

| Dimension | Weight | Signal | Score | Weighted |
|:----------|:------:|:-------|:-----:|:--------:|
| Product usage | 30% | Active seats dropped 18→11; core "route export" usage down 40% MoM | **2** | 0.60 |
| Engagement | 20% | Cancelled last QBR; slow to reply for 3 weeks | **2** | 0.40 |
| Support experience | 20% | 9 tickets in 60 days, mostly payment-timeout; 1 unresolved escalation | **2** | 0.40 |
| Sentiment | 15% | Last NPS = 4 ("frustrated with reliability") | **2** | 0.30 |
| Account fit / stakeholder | 15% | 🚩 Champion (their Ops Director) left the company last month | **1** | 0.15 |
| **TOTAL** | 100% | | | **1.85 / 5 → 🔴 RED** |

## Health Level & Triggers

| Level | Score range | Meaning | Trigger / play |
|:------|:-----------:|:--------|:---------------|
| 🟢 Green | 3.6–5.0 | Healthy; on track | Maintain; watch for expansion |
| 🟡 Yellow | 2.6–3.5 | Drifting; early risk | Proactive check-in within 7 days |
| 🔴 Red | 1.0–2.5 | At risk of churn | Save-play: owner + plan within 3 days |

## Notes / Risk Factors
- **Compound risk:** the departed champion + declining usage + the unresolved payment-timeout bug. This is exactly the kind of silent churn Acme used to discover only at renewal.
- Renewal is 3 months out — enough runway to save *if* we act now.

## Action Log
| Date | Action | Owner | Result |
|:-----|:-------|:------|:-------|
| 2026-07-02 | Save-play triggered on Red; Dara to reach the new Ops lead, not just ticket-filers | Dara | Meeting booked |
| 2026-07-05 | Diagnosed root cause = payment-timeout bug + lost institutional knowledge after champion left | Dara + Sothea | Confirmed |
| 2026-07-08 | Re-onboarding session for the new Ops lead + tied usage back to their cost-per-route goal | Dara | New champion engaged |
| 2026-07-10 | Escalated payment-timeout with evidence; PM committed a fix this cycle (feedback loop) | Sothea → PM | On roadmap |
| 2026-07-24 | Re-scored: usage recovering, new champion active → 🟡 Yellow (2.9) | Dara | Trending to save |

---

*Template for the [Support & Customer Success Lead Playbook](../README.md)*
