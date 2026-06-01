# [Platform] — Decisions Needed Before Building

**Project:** [Platform] (e-commerce marketplace)
**Document type:** Decision checklist (blockers)
**Status:** 🚧 Open — resolve these to unblock the MVP

> The docs are ready; these are the **decisions and actions** the team still has to make before real building can start. Each is a blocker, not a document. Owner + a "decide by" date turns each into an action. Pull these into [todo.md](./todo.md) and track unresolved ones in the [risk-register](./risk-register.md).

---

## 🔴 Blockers (must resolve before MVP build)

| # | Decision needed | Why it blocks | Owner | Decide by |
|:--|:----------------|:--------------|:------|:---------:|
| 1 | **Who builds the product?** (in-house dev, hire, co-founder, or agency) | Responsibilities assign all Product/Tech/Eng to "[Developer]" but no one currently holds that role | [Lead] | _TBD_ |
| 2 | **Platform choice** — Vendure vs Medusa vs custom | Everything technical depends on this; multi-vendor support is the deciding factor | [Developer] | _TBD_ |
| 3 | **Payment + payout provider** | No checkout or seller withdrawal without it | [Finance Lead] | _TBD_ |
| 4 | **Commission rate / revenue mechanics** | The business model can't be validated without it | [Finance Lead] / [Lead] | _TBD_ |
| 5 | **Is the business registered?** | Needed before taking real money | [Legal Lead] | _TBD_ |
| 6 | **KYC required? (sellers / buyers)** | Shapes the registration flow & data we collect | [Legal Lead] | _TBD_ |

## 🟡 Important (resolve during Foundation phase)

| # | Decision needed | Owner | Decide by |
|:--|:----------------|:------|:---------:|
| 7 | Return / refund policy | [Legal Lead] | _TBD_ |
| 8 | Data-retention periods (e.g. receipts) | [Legal Lead] | _TBD_ |
| 9 | MVP scope freeze — which user stories are in vs. deferred | [Lead] | _TBD_ |
| 10 | First vendor cohort committed for pilot | [Marketing Lead] | _TBD_ |
| 11 | Hosting / infrastructure | [Developer] | _TBD_ |

---

## How to clear this list
1. Put each blocker on the agenda of the next [weekly meeting](./weekly-meeting.md).
2. Assign an **owner** and a **decide-by date** (fill the `_TBD_` cells).
3. When decided, **record the decision** in the relevant doc ([tech-stack](./tech-stack.md), [business-model-canvas](./business-model-canvas.md), etc.) — don't leave it only in someone's head.
4. Move the action into [todo.md](./todo.md); check it off when done.

> **The single most important one is #1 (who builds it).** A marketplace with no builder doesn't ship, no matter how good the docs are.

---

*Internal working document · `startup/draft/project-hub/`*
