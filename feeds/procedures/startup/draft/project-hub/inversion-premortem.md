# [Platform] — Inversion Pre-Mortem: "How Would We Guarantee Failure?"

**Project:** [Platform] (e-commerce marketplace)
**Document type:** Pre-mortem (inversion thinking)
**Status:** 🚧 Draft — for team discussion
**Related:** [risk-register.md](./risk-register.md) · [decisions-needed.md](./decisions-needed.md) · [five-whys-no-builder.md](./five-whys-no-builder.md) · [Inversion Principle](../../../../concepts/articles/09-inversion-principle.md)

> **Inversion** (Charlie Munger: *"invert, always invert"*) flips the question. Instead of *"how do we make [Platform] succeed?"* we ask **"how would we *guarantee* it fails?"** — then make sure we do the **opposite** of each. Failure modes are easier to see than success paths, and avoiding the obvious ways to fail is half the battle. This is a forward-looking **pre-mortem**: imagine it's a year from now and the project is dead — *why?*

---

## ☠️ "How to guarantee [Platform] fails" → ✅ "So we must…"

| # | A sure way to FAIL | → The inverse: what we MUST do | Owner |
|:--|:-------------------|:-------------------------------|:------|
| 1 | **Never assign a builder** — keep planning, never ship code | Get a technical builder with an owner + deadline ([five-whys](./five-whys-no-builder.md), [decisions-needed](./decisions-needed.md) #1) | [Lead] |
| 2 | **Plan forever, never launch** — polish docs instead of shipping an MVP | Freeze MVP scope; ship one real end-to-end transaction fast ([roadmap](./roadmap.md) Phase 1) | [Lead] |
| 3 | **Launch with no sellers AND no buyers** — ignore the two-sided cold start | Seed vendors first (via [Partner Org]); don't open to buyers until there's something to buy ([vendor-pipeline](./vendor-pipeline.md)) | [Marketing Lead] |
| 4 | **Let money/payouts break** — sellers don't get paid, buyers get charged wrong | Get payments + weekly payouts rock-solid before launch; reconcile every transaction | [Finance Lead] |
| 5 | **Allow scams & fake products** — kill buyer trust on day one | Seller verification, reviews, reporting, fast suspension ([user-stories](./user-stories.md) admin) | [Lead] |
| 6 | **Skip legal/registration** — operate illegally, mishandle private data | Register the business; define data-privacy, retention, refund, KYC ([decisions-needed](./decisions-needed.md)) | [Legal Lead] |
| 7 | **Pick the wrong tech & rebuild later** — commit to a platform that can't do multi-vendor | Validate multi-vendor support *before* committing ([tech-stack](./tech-stack.md)) | [Developer] |
| 8 | **Charge nothing / charge wrong** — no validated revenue model | Decide & test the commission rate with real transactions ([business-model-canvas](./business-model-canvas.md)) | [Finance Lead] |
| 9 | **Depend on one person/partner** — single point of failure | Document everything; diversify beyond [Partner Org]; cross-train | [Lead] |
| 10 | **Let decisions rot & re-argue them** — burn time on the same debates | Decide with owners + deadlines; write decisions down same-day ([team-collaboration](./team-collaboration.md)) | All |
| 11 | **Ignore users** — build what we assume, never ask | Talk to real buyers & sellers; validate the canvas assumptions early | [Marketing Lead] |
| 12 | **Burn out the tiny team** — overcommit, no focus | Phase the work ([roadmap](./roadmap.md)); protect focus; one owner per area | [Lead] |

---

## 🎯 The biggest failure modes (do NOT let these happen)

From the list, the **3 most lethal** for this team right now:

1. **#1 No builder** — a marketplace is software; no builder = no product. *(This is also the [Five Whys](./five-whys-no-builder.md) root cause.)*
2. **#3 Two-sided cold start** — launching empty (no sellers or no buyers) kills the marketplace before it starts.
3. **#2 Perpetual planning** — the team's current strength (great docs) becomes the trap if it never converts to a shipped MVP.

---

## 🔁 How to use this

- Treat the **left column as a "do-not-do" list** — if you catch the team doing any of them, stop.
- The **right column feeds [todo.md](./todo.md)** and the [roadmap](./roadmap.md).
- Re-run this pre-mortem at each major phase ([roadmap](./roadmap.md)) — new failure modes appear as the project grows.
- Pair with [risk-register.md](./risk-register.md): inversion *finds* the failure modes; the risk register *tracks & mitigates* them.

> **The inversion mindset:** you don't need a genius plan to succeed — you mostly need to **not do the obvious things that guarantee failure.** Avoid stupidity; success often follows.

---

*Internal working document · `startup/draft/project-hub/`*
