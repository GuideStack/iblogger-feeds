# Template: Metric Definition

> **How to use:** Fill one of these for every metric you certify into the single source of truth (see [04 — Metrics & SSOT](../04-metrics-and-single-source-of-truth.md)). The goal is that no two people can ever compute the metric differently. The **caveats** section is where future arguments go to die — be exhaustive.

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

# Metric: [CANONICAL NAME]

| Field | Value |
|:------|:------|
| **Name** | [Canonical name] |
| **Aliases (to retire)** | [old/competing names] |
| **Definition** | [one plain-English sentence a non-analyst understands] |
| **Formula** | [exact computation] |
| **Grain** | [what one row/unit represents] |
| **Source** | [upstream certified table(s)] |
| **Owner** | [named accountable person] |
| **Certified status** | [🟢 Certified / 🟡 Exploratory] · reviewed [YYYY-MM-DD] |
| **Refresh / freshness** | [cadence + max acceptable delay] |

**Caveats & edge cases:**
- [exclusions: refunds, test accounts, internal users]
- [time basis: booking vs recognition vs event date]
- [known limitations]

**Change history:**
- [YYYY-MM-DD] [what changed + why]

---

## ─── FILLED EXAMPLE ───────────────────────────────────────────────

---

# Metric: Active Customer

| Field | Value |
|:------|:------|
| **Name** | Active Customer |
| **Aliases (to retire)** | "Active User", "MAU (sales deck)", "logged-in customer" |
| **Definition** | A paying customer account that completed at least one purchase in the trailing 30 days. |
| **Formula** | `COUNT(DISTINCT customer_id)` from `marts.orders` where `order_status = 'completed'` and `order_date >= current_date - 30` |
| **Grain** | One row per distinct customer account (not per order, not per user-seat) |
| **Source** | `marts.orders` (certified) ← `staging.orders` ← app `orders` source (data contract in place) |
| **Owner** | Sokha (Revenue domain) |
| **Certified status** | 🟢 Certified · reviewed 2026-07-02 |
| **Refresh / freshness** | Hourly; max acceptable delay 2h (monitored) |

**Caveats & edge cases:**
- **Excludes** internal/test accounts (`is_internal = true`) and accounts whose only order was later fully refunded.
- **Trailing 30 days** is rolling, not calendar-month — do not compare directly to calendar MAU.
- Counts the **customer account**, so a 5-seat team account = 1 active customer (use "Active Seats" for the seat view).
- Refund handling: an order refunded within the window still counts as activity *unless* it was the customer's only order (then excluded).

**Change history:**
- 2026-07-02 Certified. Reconciled the three prior definitions; chose account-grain + completed-order basis with Finance & Sales in the room. Retired "Active User" alias.

---

*Template for the [Data & Analytics Lead Playbook](../README.md)*
