# Template: Design Critique

> **How to use:** A structured agenda for a single critique session, from [04 — Critique & Quality](../04-critique-and-quality.md). The **presenter** fills the top half before the session (context, goals, scoped ask); the **facilitator** (you, the Designer Lead) captures decisions and actions at the end. The single most important field is **"Feedback I want"** — it stops the room solving the wrong problem. Keep it kind, specific, and tied to goals — critique the work, never the person.

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

# Critique — [WORK / FEATURE] · [YYYY-MM-DD]

**Presenter:** [NAME]   **Facilitator:** [NAME]   **Stage:** [Early explore / Mid-flight / Near-final]

## 1. Context
- **Problem:** [what user problem this solves]
- **User & goal:** [who, and what they're trying to do]
- **Constraints:** [tech / time / brand / scope]

## 2. Feedback I want (scoped ask)
- ✅ Give me feedback on: [ ]
- ⛔ Already decided, please don't relitigate: [ ]

## 3. Critique Rounds
**Round A — Clarifying questions**
- [ ]

**Round B — Feedback vs the goals**
- [ ]

**Round C — Options (not mandates)**
- [ ]

## 4. Decisions & Actions
| Decision | Acting on it? | Owner | By when |
|:---------|:-------------:|:------|:--------|
| [ ] | Yes / Parked | [ ] | [ ] |

**Parked / out of scope today:** [ ]

---

## ─── FILLED EXAMPLE ───────────────────────────────────────────────

---

# Critique — Checkout: Payment Step Redesign · 2026-07-09

**Presenter:** Sary   **Facilitator:** Lakena (Designer Lead)   **Stage:** Mid-flight

## 1. Context
- **Problem:** 29% of users drop on the payment step (analytics); they can't tell which fields are required.
- **User & goal:** A returning shopper trying to pay quickly on mobile.
- **Constraints:** Must use the new token foundation; payment provider's iframe can't be restyled; ship in 2 sprints.

## 2. Feedback I want (scoped ask)
- ✅ Give me feedback on: the required-field treatment, the error-state copy, and the mobile button placement.
- ⛔ Already decided, please don't relitigate: the single-page (vs multi-step) layout — validated with 5 users last sprint.

## 3. Critique Rounds
**Round A — Clarifying questions**
- Rithy: Is the sticky CTA covering the last field on small screens? → Sary: yes on iPhone SE, needs fixing.
- Lakena: Does the provider iframe inherit our focus ring? → Sary: no, that's an a11y gap.

**Round B — Feedback vs the goals**
- The required asterisks are low-contrast (fails our AA target) — works against the "can't tell what's required" goal.
- Error copy "Invalid input" doesn't tell the user *how* to fix it — likely a driver of the drop-off.

**Round C — Options (not mandates)**
- What if required fields used a label + helper text instead of just an asterisk?
- What if the CTA anchored above the keyboard on mobile so it never hides a field?

## 4. Decisions & Actions
| Decision | Acting on it? | Owner | By when |
|:---------|:-------------:|:------|:--------|
| Replace asterisk-only with label + helper text | Yes | Sary | next crit |
| Rewrite error copy to be actionable | Yes | Sary | next crit |
| Fix sticky CTA hiding last field on small screens | Yes | Sary | next crit |
| Add visible focus ring around provider iframe wrapper | Yes (a11y) | Sary + Eng | this sprint |

**Parked / out of scope today:** single-page vs multi-step layout (already validated); saved-card UI (separate ticket).

---

*Template for the [Designer Lead Playbook](../README.md)*
