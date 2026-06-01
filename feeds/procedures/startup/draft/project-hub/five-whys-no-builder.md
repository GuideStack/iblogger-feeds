# [Platform] — Five Whys: "No One Builds the Product"

**Project:** [Platform] (e-commerce marketplace)
**Document type:** Root-cause analysis (Five Whys)
**Status:** 🚧 Draft — for team discussion
**Related:** [decisions-needed.md](./decisions-needed.md) (Blocker #1) · [team-collaboration.md](./team-collaboration.md) (Reflection step) · [Five Whys technique](../../../../concepts/articles/02-five-whys-technique.md)

> **Five Whys** asks "why?" repeatedly to move past the *symptom* to the *root cause*. We ask **why**, not **who** — this is process analysis, not blame ([don't kill the goat](./team-collaboration.md)). The answers below are a **working hypothesis** for the team to confirm or correct in a meeting.

---

## 🔴 The Problem (Symptom)

> The product isn't being built. The team has strong planning docs, but no MVP progress — because the [responsibilities matrix](./responsibilities.md) assigns Product, Technology & Engineering all to **"[Developer]"**, and no one currently holds that role.

---

## 🔍 The Five Whys

```
PROBLEM: No one is building the product.
   │
   ▼
WHY 1 — Why is no one building it?
        → Because the team has no developer / technical builder.
   │
   ▼
WHY 2 — Why is there no developer?
        → Because the 4 founders are non-technical (Lead, Finance,
          Marketing, Legal) and a builder was never recruited or assigned.
   │
   ▼
WHY 3 — Why was a builder never recruited or assigned?
        → Because the team hasn't decided HOW to get one
          (hire? technical co-founder? agency? no-code/low-code?).
   │
   ▼
WHY 4 — Why hasn't that decision been made?
        → Because it depends on money + the platform choice, which are
          also unresolved — so it keeps getting deferred.
   │
   ▼
WHY 5 — Why does it keep getting deferred?
        → Because no single owner is accountable for "how we build,"
          and there's no deadline forcing the decision.
   │
   ▼
ROOT CAUSE ▼
```

---

## 🎯 Root Cause

> **There is no owner and no deadline for the "how do we build this?" decision** — so the most important question for an e-commerce *product* has no one driving it and never gets forced. Everything technical is blocked behind it.

This is a classic founding-team gap: a marketplace is fundamentally a *software product*, but the team is staffed for business/ops/legal/marketing, with the build itself left as an unowned placeholder.

---

## ✅ Countermeasures (fix the root cause, not the symptom)

| # | Action | Owner | By |
|:--|:-------|:------|:--:|
| 1 | **Assign an owner** for the "how we build" decision (default: [Lead]) | [Lead] | _now_ |
| 2 | **Set a hard deadline** to decide the build approach (forces the choice) | [Lead] | _TBD_ |
| 3 | **Choose the build path:** technical co-founder · hire a developer · agency · no-code/low-code MVP | [Lead] | _by #2_ |
| 4 | Make the platform + budget decisions it depends on ([tech-stack](./tech-stack.md), [business-model-canvas](./business-model-canvas.md)) | [Developer] / [Finance Lead] | _TBD_ |
| 5 | **Record the decision** in [decisions-needed.md](./decisions-needed.md) and update [roles.md](./roles.md) with the real builder | [Lead] | _after #3_ |

> **Symptom fix (wrong):** "let's write more specs." **Root-cause fix (right):** "someone owns getting a builder, with a deadline." Specs don't ship; builders do.

---

## 🔁 Prevention (so this class of problem doesn't recur)

- **Every critical area has a named owner** — including the uncomfortable "we don't have this skill" gaps. An unowned `[Placeholder]` in [responsibilities.md](./responsibilities.md) is a red flag, not a plan.
- **Decisions that block others get a deadline**, tracked in [decisions-needed.md](./decisions-needed.md).
- Run this **Five Whys** on any recurring pain — surface it at the [weekly meeting](./weekly-meeting.md), ask *why* five times, fix the process.

---

*Internal working document · `startup/draft/project-hub/`*
