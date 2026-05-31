# Template: SLA Policy

> **How to use:** Define your priority tiers, response & resolution targets per tier, coverage hours, and escalation triggers. Set targets you can actually hit at current staffing, then tighten. Align severities with the cross-team [Bug & Incident Flow](../../software-delivery/02-bug-and-incident-flow.md). See [03 — SLAs & Ticket Operations](../03-slas-and-ticket-operations.md).

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

# SLA Policy — [WORKSPACE / PRODUCT]

**Owner:** [NAME] · **Effective:** [YYYY-MM-DD] · **Review cadence:** [quarterly]

## Coverage Hours
- **Standard:** [days / hours / timezone]
- **After-hours / 24×7:** [which tiers, via what rotation]

## Priority Tiers & Targets

| Priority | Definition | Response (first human) | Resolution target | Coverage |
|:---------|:-----------|:-----------------------|:------------------|:---------|
| **P1 — Critical** | [Service down / data loss] | [ ] | [ ] | [ ] |
| **P2 — High** | [Major feature broken, no workaround] | [ ] | [ ] | [ ] |
| **P3 — Normal** | [Issue with a workaround] | [ ] | [ ] | [ ] |
| **P4 — Low** | [Question / cosmetic / request] | [ ] | [ ] | [ ] |

## Priority Rules
- Priority is set by **business impact** (scope × severity × workaround), not customer tone.
- The lead may re-tier (up or down) with a brief note to the customer.
- SLA clock pauses when genuinely **waiting on the customer**.

## Escalation Triggers
| Trigger | Escalate to | Within |
|:--------|:------------|:-------|
| [ ] | [ ] | [ ] |

## Internal SLO (buffer vs the SLA)
- Hit each tier's SLA [X]% of the time.

---

## ─── FILLED EXAMPLE ───────────────────────────────────────────────

---

# SLA Policy — Acme SaaS

**Owner:** Sothea (Support / CS Lead) · **Effective:** 2026-07-01 · **Review cadence:** quarterly

> Acme's first-ever SLA. Set deliberately conservative for current staffing (5 agents, business-hours + a P1 on-call rotation). Targets tighten next quarter once the backlog is cleared and the new hire ramps.

## Coverage Hours
- **Standard:** Mon–Fri, 08:00–18:00 ICT (covers our APAC + early EU customers)
- **After-hours:** **P1 only**, via a 3-person on-call rotation with a 1h page SLA

## Priority Tiers & Targets

| Priority | Definition | Response (first human) | Resolution target | Coverage |
|:---------|:-----------|:-----------------------|:------------------|:---------|
| **P1 — Critical** | Service down, data loss, payments failing for an account, all work blocked | **1 hour** | **8 hours** | 24×7 (on-call) |
| **P2 — High** | Major feature broken, significant impact, no workaround | **4 business hours** | **1 business day** | Business hours |
| **P3 — Normal** | Issue with a workaround; limited impact | **1 business day** | **3 business days** | Business hours |
| **P4 — Low** | Question, cosmetic, feature request | **2 business days** | Best effort | Business hours |

## Priority Rules
- Priority is set by **business impact**, not by how the ticket is worded. A calmly-worded outage is still P1; an angrily-worded "how do I change my logo" is still P4.
- Sothea (or senior agent on duty) may re-tier with a one-line note to the customer.
- The SLA clock pauses on "pending customer." A courteous reminder goes out at 3 days; auto-close at 7 with easy reopen.

## Escalation Triggers
| Trigger | Escalate to | Within |
|:--------|:------------|:-------|
| Confirmed bug / data issue | Engineering (L3) per OLA | Ack 30 min (P1) / same day (P2) |
| P1 unresolved at 50% of resolution target | Eng on-call + Sothea | Immediately |
| Any production outage | Incident process — see [Bug & Incident Flow](../../software-delivery/02-bug-and-incident-flow.md) | Per severity (P1↔SEV-1) |
| Account flagged Red + open escalation near renewal | CSM + Sothea (save-play) | Same day |

## Internal SLO (buffer vs the SLA)
- Hit each tier's response SLA **95%** of the time; resolution SLA **90%**. Internal targets run ~25% tighter than the customer-facing SLA so we have buffer before a real breach.

---

*Template for the [Support & Customer Success Lead Playbook](../README.md)*
