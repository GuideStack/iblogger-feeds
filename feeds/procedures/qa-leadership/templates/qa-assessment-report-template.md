# Template: QA State Assessment Report

> **How to use:** Produce this at the end of Phase 2 (days 15–30) using the [QA Assessment procedure](../02-qa-assessment.md). Keep **findings (facts)** and **recommendations (opinions)** clearly separated — this protects your credibility. Review it privately with your manager *before* sharing widely.

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

# QA State Assessment — [TEAM / PRODUCT]

**Author:** [NAME]
**Date:** [YYYY-MM-DD]
**Period observed:** [start] – [end]
**Audience:** [Eng Manager, then team]

---

## 1. Executive Summary
> 3–5 sentences. The overall state, the top 3 pains, and your headline recommendation.

[SUMMARY]

---

## 2. Maturity Scorecard

| Dimension | Score (1–5) | Evidence |
|:----------|:-----------:|:---------|
| People | [ ] | [evidence] |
| Process | [ ] | [evidence] |
| Tools | [ ] | [evidence] |
| Environments | [ ] | [evidence] |
| Coverage | [ ] | [evidence] |
| Metrics | [ ] | [evidence] |

*(1 = Chaotic, 2 = Reactive, 3 = Defined, 4 = Managed, 5 = Optimized)*

---

## 3. Findings (Facts)
> What is true today. No judgment, just evidence.

- **People:** [finding]
- **Process:** [finding]
- **Tools:** [finding]
- **Environments:** [finding]
- **Coverage:** [finding]
- **Metrics:** [finding]

---

## 4. Top Pains (Ranked)

| Pain | Frequency | Cost | Priority | Root cause |
|:-----|:---------:|:-----|:--------:|:-----------|
| [pain] | [ ] | [ ] | 🔴/🟡/🟢 | [cause] |

---

## 5. Recommendations (Opinions)
> Clearly separated from findings. Tied to the pains above.

| # | Recommendation | Addresses | Impact | Effort |
|:--|:---------------|:----------|:------:|:------:|
| 1 | [action] | [pain] | H/M/L | H/M/L |

---

## 6. What's Working (Don't Break)
> Equally important. List what's good so you don't accidentally remove it.

- [strength]

---

## ─── FILLED EXAMPLE (excerpt) ─────────────────────────────────────

---

**Executive Summary:** QA is reactive and release-time heavy. The team is skilled but firefights. Top 3 pains: an 18%-flaky E2E suite blocking PRs, 3-day manual regression per release, and no escaped-defect tracking. Headline recommendation: stabilize the E2E suite first — it unblocks everything else.

**Scorecard:** People 4 · Process 2 · Tools 3 · Environments 2 · Coverage 2 · Metrics 1

**Top pain:** Flaky E2E — Frequency: daily — Cost: ~2h dev time/PR + lost trust — 🔴 High — Root cause: tests share state and hit a live third-party sandbox.

**Don't break:** Strong exploratory testing culture; testers genuinely understand the product domain.

---

*Template for the [QA Leadership Playbook](../README.md)*
