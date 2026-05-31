# Template: Prioritization Matrix

> **How to use:** Use this when several epics are competing for the top of the backlog and you need a *defensible* order. Two scoring methods are provided — a quick **Value vs Effort** grid and a numeric **WSJF** table. Pick one, score consistently, and remember: the framework makes your reasoning visible, it doesn't make the decision for you. You still own the final order. See [05 — Prioritization & Value](../05-prioritization-and-value.md).

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

### Option A — Value vs Effort grid

```
            HIGH VALUE
                │
    BIG BETS    │   QUICK WINS
   (schedule)   │   (do now)
                │
  ──────────────┼──────────────  EFFORT →
                │
    AVOID /     │   FILL-INS
   DEPRIORITIZE │
                │
            LOW VALUE
```

Place each epic in a quadrant, then rank within "do now" first.

### Option B — WSJF score table

> **WSJF = Cost of Delay ÷ Job Size**, where **Cost of Delay = User/Business Value + Time Criticality + Risk/Opportunity.** Score each component on a relative scale (e.g. 1–10). Higher WSJF → do it sooner.

| Epic | Value | Time Crit. | Risk/Opp | Cost of Delay | Job Size | WSJF | Rank |
|:-----|:-----:|:----------:|:--------:|:-------------:|:--------:|:----:|:----:|
| [epic] | [ ] | [ ] | [ ] | [sum] | [ ] | [CoD÷size] | [ ] |
| [epic] | [ ] | [ ] | [ ] | [sum] | [ ] | [ ] | [ ] |
| [epic] | [ ] | [ ] | [ ] | [sum] | [ ] | [ ] | [ ] |

**Decision:** [The order you're committing to, and the one-line "why" for the top item.]

---

## ─── FILLED EXAMPLE ───────────────────────────────────────────────

---

Sreypov has five epics fighting for the top of the Riel Wallet backlog. She scores them with WSJF (value team estimated job size at refinement).

### Value vs Effort (quick read)

```
            HIGH VALUE
                │
   Bill pay     │   Send-by-phone
   (big bet)    │   Frictionless top-up   (do now)
                │
  ──────────────┼──────────────  EFFORT →
                │
   Dark mode    │   Profile photo
   (avoid now)  │   (fill-in)
                │
            LOW VALUE
```

### WSJF score table

| Epic | Value | Time Crit. | Risk/Opp | Cost of Delay | Job Size | WSJF | Rank |
|:-----|:-----:|:----------:|:--------:|:-------------:|:--------:|:----:|:----:|
| Send money by phone number | 10 | 8 | 6 | 24 | 5 | **4.8** | 🥇 1 |
| Frictionless top-up | 8 | 6 | 4 | 18 | 5 | **3.6** | 🥈 2 |
| Bill pay | 9 | 5 | 5 | 19 | 13 | **1.5** | 🥉 3 |
| Profile photo | 3 | 2 | 1 | 6 | 3 | **2.0** | 4 |
| Dark mode | 2 | 1 | 1 | 4 | 8 | **0.5** | 5 |

**Decision:** Order = Send-by-phone → Top-up → (Profile photo as a fill-in) → Bill pay → Dark mode.
**Why the top item:** *Send money by phone number* has the highest cost of delay (it removes the #1 onboarding friction and directly drives this quarter's 34% → 60% activation outcome) and is small — exactly the WSJF sweet spot. Bill pay is genuinely valuable but its large job size pushes it down; it'll be sliced into smaller stories before it competes for the top again.

> Note how WSJF surfaced a non-obvious call: *Profile photo* scored higher than *Bill pay* on WSJF (2.0 vs 1.5) purely because it's tiny — but Sreypov still ranks it as a fill-in, not above the activation work, because it doesn't serve the quarter's outcome. The framework informs the order; the PO owns it.

---

*Template for the [Product Owner Playbook](../README.md)*
