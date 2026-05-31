# Template: Design Assessment

> **How to use:** This is the output of [02 — Design Assessment](../02-design-assessment.md). Score each of the six dimensions on the **1–5 maturity scale**, anchor every finding to a fact (a count, a screenshot, a metric), then rank recommendations by **impact × effort**. Keep facts and recommendations clearly separated. Review it with your manager **privately first** before any wide share.

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

# Design Assessment — [PRODUCT / TEAM]

**Author:** [YOUR NAME], Designer Lead
**Date:** [YYYY-MM-DD]
**Reviewed with manager:** [Y/N]

## 📊 Scorecard (1–5 maturity)

| # | Dimension | Score | One-line evidence |
|:--|:----------|:-----:|:------------------|
| 1 | Design System & Consistency | [1–5] | [count / screenshot] |
| 2 | UX / Research Practice | [1–5] | [cadence / evidence ratio] |
| 3 | Design–Dev Handoff | [1–5] | [churn / parity] |
| 4 | Design Ops & Tooling | [1–5] | [source of truth / naming] |
| 5 | Accessibility | [1–5] | [contrast / keyboard / target] |
| 6 | Team Skills | [1–5] | [bus factor / gaps] |

## 🔍 Findings (facts only)
- **Dimension 1 —** [fact + evidence]
- **Dimension 2 —** [fact + evidence]
- *(…through 6)*

## 🎯 Recommendations (ranked by impact × effort)
| Priority | Recommendation | Impact | Effort | Quadrant |
|:--------:|:---------------|:------:|:------:|:---------|
| 1 | [ ] | H/M/L | H/M/L | Do Now / Schedule / Fill-in |

## 🆘 What I need to act on this
- [resourcing / decision / access]

---

## ─── FILLED EXAMPLE ───────────────────────────────────────────────

---

# Design Assessment — Iblogger Web App

**Author:** Lakena, Designer Lead
**Date:** 2026-06-26
**Reviewed with manager:** Y (Vichea, day 27)

## 📊 Scorecard (1–5 maturity)

| # | Dimension | Score | One-line evidence |
|:--|:----------|:-----:|:------------------|
| 1 | Design System & Consistency | **2** | 6 button styles, 3 date pickers in prod; no tokens; ~25% systemized |
| 2 | UX / Research Practice | **1** | Zero usability tests in the last year; decisions cite stakeholder, not user |
| 3 | Design–Dev Handoff | **2** | ~40% of designs reworked after dev starts; states often unspecified |
| 4 | Design Ops & Tooling | **2** | 3 "final" copies of the main file; layers named `Frame 482` |
| 5 | Accessibility | **2** | Primary CTA fails AA contrast (3.1:1); no keyboard focus order; no WCAG target |
| 6 | Team Skills | **2** | Bus factor 1 on the only person who knows the icon set; no one runs research |

## 🔍 Findings (facts only)
- **System —** Live UI has 6 distinct primary buttons (screenshots A1–A6). No color/spacing tokens; values hard-coded per screen. A rebrand today would touch ~400 layers by hand.
- **Research —** No usability sessions on record. Of the last 5 shipped design decisions, 0 cite a user insight; 4 cite a stakeholder preference (HiPPO).
- **Handoff —** Sampled 10 recent features: 4 were reworked post-dev because empty/error/loading states weren't specified.
- **Ops —** `App_FINAL`, `App_FINAL_v2`, `App_REAL_use_this` all exist; engineers report opening the wrong one weekly.
- **Accessibility —** Primary CTA blue-on-blue measures 3.1:1 (AA needs 4.5:1). Checkout cannot be completed by keyboard alone. No stated conformance target.
- **Team —** 3 designers. Only Rithy understands the icon system; only Lakena (new) has run usability tests. Sary wants to grow into research.

## 🎯 Recommendations (ranked by impact × effort)
| Priority | Recommendation | Impact | Effort | Quadrant |
|:--------:|:---------------|:------:|:------:|:---------|
| 1 | Color + spacing token foundation in design & code | H | L | **Do Now** |
| 2 | Consolidate 6 buttons → 1 with variants | H | L | **Do Now** |
| 3 | Fix AA contrast on primary CTA + add focus order | H | L | **Do Now** |
| 4 | Stand up a 5-user usability test every sprint | H | M | **Schedule** |
| 5 | Single source of truth + naming convention | M | L | **Do Now** |
| 6 | Full component library (top 12 components) | H | H | **Schedule** |

## 🆘 What I need to act on this
- Eng time to wire tokens into code (est. 3 days)
- A standing recruiting channel for usability participants (Support's customer list)
- Agreement on WCAG 2.2 AA as our conformance target

---

*Template for the [Designer Lead Playbook](../README.md)*
