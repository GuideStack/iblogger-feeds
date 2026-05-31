# Template: Support & CS Assessment Report

> **How to use:** This is the output of the [Phase 2 Assessment procedure](../02-support-assessment.md). Score six dimensions on a **1–5 maturity scale**, attach evidence to every score, then prioritize the top 3 fixes by **impact × effort**. Lead with facts; separate recommendations. Review with your manager privately before sharing widely.

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

# Support & CS Assessment — [WORKSPACE / TEAM]

**Author:** [YOUR NAME], Support / CS Lead
**Date:** [YYYY-MM-DD]
**Period reviewed:** [date range]

## 1. Scorecard (1 = Chaotic · 5 = Optimizing)

| # | Dimension | Discipline | Score (1–5) | Evidence (number or quote) |
|:--|:----------|:-----------|:-----------:|:---------------------------|
| 1 | Responsiveness & SLAs | Support | [ ] | [ ] |
| 2 | Quality & CSAT | Support | [ ] | [ ] |
| 3 | Knowledge & deflection | Both | [ ] | [ ] |
| 4 | Escalation & eng feedback loop | Both | [ ] | [ ] |
| 5 | Retention/churn & health | CS | [ ] | [ ] |
| 6 | Team skills & morale | Both | [ ] | [ ] |

## 2. Key Facts (no opinions)
- [Metric / observation]

## 3. The Support-vs-CS Gap
- [Which discipline is starved? e.g. "Support is X; CS is effectively absent."]

## 4. Top 3 Recommendations (prioritized)

| # | Fix | Impact | Effort | Quadrant | Candidate owner |
|:--|:----|:-------|:-------|:---------|:----------------|
| 1 | [ ] | [H/M/L] | [H/M/L] | [Do-now / Schedule] | [ ] |
| 2 | [ ] | [ ] | [ ] | [ ] | [ ] |
| 3 | [ ] | [ ] | [ ] | [ ] | [ ] |

## 5. What I Need
- [Support / decision / budget / headcount]

---

## ─── FILLED EXAMPLE ───────────────────────────────────────────────

---

# Support & CS Assessment — Acme SaaS, Support & CS Team

**Author:** Sothea, Support / Customer Success Lead
**Date:** 2026-06-26
**Period reviewed:** Q1 2026 + first 3 weeks of tenure

## 1. Scorecard

| # | Dimension | Discipline | Score | Evidence |
|:--|:----------|:-----------|:-----:|:---------|
| 1 | Responsiveness & SLAs | Support | **1** | No SLAs defined. Median first response 31h; ~180-ticket backlog, oldest 17 days |
| 2 | Quality & CSAT | Support | **2** | CSAT not surveyed. Reopen rate ~22% (estimated from re-filed tickets) |
| 3 | Knowledge & deflection | Both | **2** | KB exists but ~40% stale; no deflection metric; answers live in agents' heads |
| 4 | Escalation & eng feedback loop | Both | **1** | Bugs emailed to Eng, no ack, no tracking. "Payment-timeout" reported 5+ months, never fixed |
| 5 | Retention/churn & health | CS | **1** | No health score. 3 logos churned last quarter — all surprises. No renewal forecast |
| 6 | Team skills & morale | Both | **2** | 5 agents, no onboarding doc; 2 working through lunch daily; 1 hasn't taken PTO in 4 months |

## 2. Key Facts
- 180-ticket backlog growing ~10%/week; no priority tiers, so emergencies queue behind FAQs.
- "Payment-timeout" theme = **412 tickets in Q1 (18% of volume)**, cited in customer notes for 2 of the 3 churns.
- ~60 agent-hours/quarter spent re-answering the payment-timeout issue.
- No CSAT, NPS, or health data collected anywhere.

## 3. The Support-vs-CS Gap
Support is barely functional (score 1–2) and **Customer Success effectively does not exist (1)** — there is no proactive motion at all. Churn is discovered at renewal, never prevented. This is the biggest hidden risk: the loud backlog gets attention while silent churn quietly costs more.

## 4. Top 3 Recommendations

| # | Fix | Impact | Effort | Quadrant | Candidate owner |
|:--|:----|:-------|:-------|:---------|:----------------|
| 1 | Publish SLA + tiers; run a backlog burn-down | High | Low | **Do-now** | Sothea + team |
| 2 | Build the eng feedback loop (OLA + evidenced cases) — kill the payment-timeout black hole | High | Med | **Schedule** | Sothea + Eng + PM |
| 3 | Stand up a basic Green/Yellow/Red health score to catch at-risk accounts | High | Med | **Schedule** | Sothea + CSMs |

## 5. What I Need
- One additional agent to sustain coverage during the burn-down.
- Priya's backing on an escalation OLA with Engineering.
- Air cover to push back on Sales over-promising go-live dates (a root cause of early churn).

---

*Template for the [Support & Customer Success Lead Playbook](../README.md)*
