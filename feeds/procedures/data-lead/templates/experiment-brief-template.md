# Template: Experiment Brief

> **How to use:** Fill this out **before** launching any experiment (see [05 — Experimentation & Decisions](../05-experimentation-and-decisions.md)). Writing the hypothesis and decision rule up front is your single best defense against p-hacking and HARKing. Once it's running, do not change the primary metric or stop early.

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

# Experiment: [NAME] · #[ID]

| Field | Value |
|:------|:------|
| **Owner** | [Data Lead + PM] |
| **Status** | [Draft / Running / Decided] |
| **Decision it informs** | [what action each outcome leads to] |

**Hypothesis:** We believe [change] will cause [effect] because [reasoning]. (Stated *before* the test.)

**Primary metric:** [the ONE metric that decides success]

**Guardrail metrics (must NOT get worse):**
- [metric + threshold]

**Design:**
- Unit of randomization: [user / session / account]
- Variants: [A control vs B treatment]
- Eligibility / exclusions: [who's in]

**Sample size & duration:**
- Minimum detectable effect: [%]
- Required sample per arm: [N] · Significance: [p<0.05] · Power: [0.8]
- Planned duration: [until N reached, ~X days] — **no early stopping**

**Decision rule (pre-committed):**
> If [primary metric] [+X% at p<0.05] AND all guardrails hold → [ship]. Else → [iterate / kill].

**Result & decision:** [filled after the run]

---

## ─── FILLED EXAMPLE ───────────────────────────────────────────────

---

# Experiment: One-Page Checkout · #214

| Field | Value |
|:------|:------|
| **Owner** | Pich (Data Lead) + Lina (PM) |
| **Status** | Decided |
| **Decision it informs** | Whether to roll the new one-page checkout to 100% or revert |

**Hypothesis:** We believe collapsing checkout from 3 pages to 1 will **increase completed-order conversion** because we remove two drop-off points observed in funnel analysis.

**Primary metric:** Checkout conversion rate (sessions with a completed order ÷ sessions that reached checkout).

**Guardrail metrics (must NOT get worse):**
- Refund rate (≤ current 2.1%)
- Page-load p95 latency (≤ 1.8s)
- 30-day retention (no significant drop)

**Design:**
- Unit of randomization: session
- Variants: A = current 3-page checkout · B = new one-page checkout
- Eligibility: all web checkout sessions; exclude internal/test accounts

**Sample size & duration:**
- Minimum detectable effect: +2% absolute conversion
- Required sample: ~24,000 sessions per arm · p<0.05 · power 0.8
- Planned duration: ~14 days (covers two weekends) — **no early stopping**

**Decision rule (pre-committed):**
> If conversion is up ≥ +2% absolute at p<0.05 AND all three guardrails hold → ship to 100%. Else → iterate or kill.

**Result & decision:**
Conversion **+3.1%** (95% CI: +1.2% to +5.0%, p=0.004). Guardrails held (refund 2.0%, p95 1.7s, retention flat). Met the pre-set rule → **shipped to 100%**. Logged in the decision log; **revisit at +30 days** to confirm the lift held in production (it did: +2.8% realized).

---

*Template for the [Data & Analytics Lead Playbook](../README.md)*
