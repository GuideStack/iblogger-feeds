# [Platform] — Risk Register

**Project:** [Platform] (e-commerce marketplace)
**Document type:** Risk management
**Status:** 🚧 Draft (living document — review at each weekly meeting)

> Tracks known risks, their severity, and mitigations. Several entries come directly from the legal/privacy items raised in [meeting-notes.md](./meeting-notes.md). Review and update regularly. **Impact × Likelihood** drives priority.

---

## Risk Log

| # | Risk | Category | Impact | Likelihood | Priority | Mitigation | Owner |
|:--|:-----|:---------|:------:|:----------:|:--------:|:-----------|:------|
| R1 | Breach of private/sensitive information (e.g. health, ID, bank data) | Privacy/Legal | High | Med | 🔴 High | Legal research on data-protection rules; encryption; data minimization; access controls | [Legal Lead] / [Developer] |
| R2 | Unclear receipt / transaction-record retention period | Compliance | Med | Med | 🟡 Med | Legal research on required retention duration; implement retention policy | [Legal Lead] |
| R3 | KYC requirement undefined (sellers/buyers) | Compliance | Med | High | 🟡 Med | Decide if/where KYC applies; pick a verification approach | [Legal Lead] / [Lead] |
| R4 | Business not yet registered | Legal | High | High | 🔴 High | Complete business registration; research tax requirements | [Legal Lead] |
| R5 | Fraudulent sellers / scam listings | Trust & Safety | High | Med | 🔴 High | Seller verification, reporting, admin suspension, reviews | [Lead] / [Developer] |
| R6 | Payment / payout failures or disputes | Financial/Ops | High | Med | 🔴 High | Reliable payment provider; clear refund policy; transaction records | [Finance Lead] |
| R7 | Two-sided cold start (not enough buyers or sellers) | Market | High | High | 🔴 High | Seed vendors via [Partner Org]; seller-led buyer acquisition; phased pilot | [Marketing Lead] |
| R8 | Over-reliance on a single partner/network | Strategic | Med | Med | 🟡 Med | Diversify vendor sources beyond [Partner Org] | [Lead] |
| R9 | Choosing the wrong tech platform (rework later) | Technical | Med | Med | 🟡 Med | Evaluate frameworks vs. multi-vendor need before committing ([tech-stack.md](./tech-stack.md)) | [Developer] |
| R10 | Small founding team / key-person dependency | Org | Med | Med | 🟡 Med | Document processes; cross-train; clear role coverage ([roles.md](./roles.md)) | [Lead] |

---

## Priority legend
- 🔴 **High** — address now / before launch
- 🟡 **Med** — plan a mitigation, monitor
- 🟢 **Low** — accept & watch

## How to use
1. Review this register at each [weekly meeting](./weekly-meeting.md).
2. Re-score Impact × Likelihood as things change.
3. Add new risks as they surface; close risks that are resolved.

---

*Internal working document · `startup/draft/project-hub/`*
