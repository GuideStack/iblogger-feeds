# Template: Release Sign-Off Report

> **How to use:** The QA Lead fills this for every release per the [Release Sign-Off procedure](../05-release-signoff.md). The QA verdict is **fact vs criteria** — the Go/No-Go is a separate, recorded business decision. Any unmet criterion that ships must be **waived in writing**, never silently.

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

# Release Sign-Off — v[VERSION]

**Date:** [YYYY-MM-DD]
**QA Lead:** [NAME]
**Release owner:** [NAME]
**Build / RC:** [identifier]

---

## ✅ Testing Complete
- [ ] All planned test cases executed
- [ ] Critical + high priority cases pass
- [ ] Regression suite green
- [ ] Exploratory testing done on new features

## 🐞 Defects
- Open S1/S2: **[count]** (target: 0)
- In-scope fixes verified: [ ]/[ ]
- **Known issues (accepted):**
  | Issue | Severity | Workaround |
  |:------|:--------:|:-----------|
  | [ ] | [ ] | [ ] |

## 🚀 Readiness
- [ ] PO acceptance signed — by [NAME]
- [ ] Rollback plan exists & tested
- [ ] Monitoring/alerts cover new changes
- [ ] Release notes + support informed

## 🧪 QA Verdict
> Fact-based: do the results meet our exit criteria?

**[ MEETS / DOES NOT MEET ] exit criteria.**
Evidence: [summary]

## 🚦 Go / No-Go Decision
> Business decision — names required.

- **Decision:** `GO` | `NO-GO`
- **Decided by:** [PM/PO + Eng Manager]
- **Waivers (if GO with unmet criteria):** [what risk is accepted, by whom]

---

## ─── FILLED EXAMPLE (excerpt) ─────────────────────────────────────

---

# Release Sign-Off — v2026.06.2

**QA Lead:** Dara · **Release owner:** Kosal · **RC:** 2026.06.10-rc2

**Defects:** Open S1/S2: **0**. Fixes verified: 7/7.
**Known issues:** Coupon analytics chart lags ~5s (S4) — workaround: refresh.

**QA Verdict:** ✅ MEETS exit criteria. Regression green (412/412), 0 open S1/S2, PO signed.

**Go/No-Go:** `GO` — decided by Sophea (Eng Mgr) + Lina (PO). No waivers needed.

---

*Template for the [QA Leadership Playbook](../README.md)*
