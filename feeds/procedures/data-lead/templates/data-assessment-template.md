# Template: Data Assessment Report

> **How to use:** This is the output of your Phase 2 audit (see [02 — Data State Assessment](../02-data-assessment.md)). Keep findings (facts) clearly separated from recommendations (opinions). Score each of the six dimensions 1–5 with **evidence**. Review it privately with your manager before sharing widely.

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

# Data Assessment — [WORKSPACE / ORG], by [YOUR NAME]

**Date:** [YYYY-MM-DD] · **Assessor:** [NAME] · **Reviewed with:** [MANAGER]

## 1. Executive Summary
- **Overall data maturity:** [avg score] / 5
- **Top 3 pains (by impact × effort):**
  1. [pain]
  2. [pain]
  3. [pain]
- **The one-line headline:** [the single thing leadership most needs to know]

## 2. Maturity Scorecard

| # | Dimension | Score (1–5) | Evidence |
|:--|:----------|:-----------:|:---------|
| 1 | Data Quality & Trust | [ ] | [facts] |
| 2 | Pipelines & Architecture | [ ] | [facts] |
| 3 | Governance & Access | [ ] | [facts] |
| 4 | Metric Definitions / SSOT | [ ] | [facts] |
| 5 | Analytics Enablement / Self-Serve | [ ] | [facts] |
| 6 | Team Skills | [ ] | [facts] |

## 3. Findings (facts only)
- [Dimension]: [observation + number]

## 4. Prioritized Pains

| Pain | Impact | Effort | Priority | Notes |
|:-----|:------:|:------:|:--------:|:------|
| [pain] | [H/M/L] | [H/M/L] | [🔴/🟡/🟢] | [note] |

## 5. Recommendations (clearly labeled as opinion)
- [recommendation → which pain it addresses]

---

## ─── FILLED EXAMPLE (excerpt) ─────────────────────────────────────

---

# Data Assessment — Acme Co, by Pich

**Date:** 2026-06-26 · **Assessor:** Pich · **Reviewed with:** Maly (VP Eng)

## 1. Executive Summary
- **Overall data maturity:** 2.2 / 5
- **Top 3 pains:** (1) conflicting revenue definitions, (2) stale exec dashboard, (3) analysts as a ticket desk.
- **Headline:** *Leadership distrusts the dashboards because "revenue" means three different things — and the exec view is a day and a half old.*

## 2. Maturity Scorecard

| # | Dimension | Score | Evidence |
|:--|:----------|:-----:|:---------|
| 1 | Data Quality & Trust | 2 | Consumers find bugs first; no monitoring. CFO caught a double-counted-refund error in May. |
| 2 | Pipelines & Architecture | 3 | Layered models exist but transforms are partly hand-edited in the warehouse; ~2 silent failures/month. |
| 3 | Governance & Access | 2 | Access granted ad hoc; PII in `users` table unmasked and broadly readable. |
| 4 | Metric Definitions / SSOT | 2 | 3 live "revenue" definitions disagree ~8% (refunds + test accounts + booking vs ship date). No catalog. |
| 5 | Enablement / Self-Serve | 2 | ~80% of team time is reactive tickets via DM; no governed self-serve; several stale dashboards. |
| 6 | Team Skills | 3 | Strong SQL/BI; thin on experimentation stats and data-contract/pipeline engineering. |

## 3. Findings (facts)
- Exec revenue dashboard freshness: **36h** (stakeholders assume "today").
- **3** active definitions for revenue; Finance vs Sales differ by ~**8%**.
- Request queue: **27** open, median turnaround **9 days**.

## 4. Prioritized Pains

| Pain | Impact | Effort | Priority | Notes |
|:-----|:------:|:------:|:--------:|:------|
| Conflicting revenue numbers | H | M | 🔴 | Reconcile + certify first |
| Stale exec dashboard | H | L | 🔴 | Freshness monitoring = quick, visible win |
| Analysts as ticket desk | H | H | 🟡 | Needs intake + self-serve investment |
| Unmasked PII | H | M | 🔴 | Compliance risk, not just hygiene |

## 5. Recommendations (opinion)
- Reconcile & certify "revenue" in a metric layer → kills pain #1 and rebuilds trust fastest.
- Add freshness/volume monitoring on the 6 exec tables → pain #2, low effort.
- Stand up a single intake front door + start converting recurring asks to self-serve → pain #3.

---

*Template for the [Data & Analytics Lead Playbook](../README.md)*
