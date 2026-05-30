# FS Module 8: Reporting & Profit/Loss

> Part of the [Cross-Border Social Resell POS](00-overview.md). Turning all the data into the numbers the owner actually cares about.

## Summary

The whole point of tracking landed cost, channel, discounts, and returns is to answer one question honestly: **are we actually making money, and where?** This module reports real **profit/loss** — revenue minus landed cost minus fees minus returns — plus the operational numbers (stock value, COD float, channel performance) that keep the business safe. Revenue alone is a vanity number; this module refuses to show it without cost beside it.

## Users

Owner (primary), Finance, PM.

## Functional Requirements

- **RP-1:** A **Profit/Loss** view over a date range: gross revenue, total landed cost of goods sold, fees (shipping, courier, payment), returns/refunds, and **net profit**.
- **RP-2:** **Margin per product / variant**: selling price (incl. manual discounts) minus landed cost, so the owner sees true winners and losers.
- **RP-3:** **Channel performance**: orders, revenue, and margin split by **TikTok vs Facebook vs manual**, so spend follows what works.
- **RP-4:** **Stock value** report: current inventory valued at landed cost (total tied-up capital).
- **RP-5:** **COD float** report: cash shipped but not yet remitted, per courier — the money "in the wild".
- **RP-6:** **Outstanding payments**: orders awaiting payment / partially paid, so nothing is forgotten.
- **RP-7:** Reports reflect **net of returns** (from [Module 7](07-returns.md)) — a refunded sale is not counted as revenue.
- **RP-8:** All reports are **filterable** by date range, channel, product, and exportable (CSV) for the accountant.

## Acceptance Criteria

- **RP-1:** Given in a month: revenue 10,000, COGS (landed) 6,000, fees 800, refunds 500, When the P&L is viewed, Then net profit = 10,000 − 6,000 − 800 − 500 = **2,700**.
- **RP-2:** Given a product sold at 25 with landed cost 14, When margin is viewed, Then it shows 11 per unit (44%); a discounted sale at 22 shows 8 (36%).
- **RP-3:** Given 60 orders from TikTok and 40 from Facebook, When channel performance is viewed, Then revenue and margin are shown separately for each channel.
- **RP-5:** Given 60 of COD is shipped but unremitted via courier X, When COD float is viewed, Then it shows 60 outstanding for courier X.
- **RP-7:** Given a 50 sale that was fully refunded, When the P&L for that period is viewed, Then that 50 is not counted in net revenue.

## Edge Cases

- A sale and its return fall in **different months** → the refund reduces the month it occurred in, and the report makes the timing visible (no silent back-dating).
- FX changed between buying and selling → margin uses the **historical landed cost** of the units actually sold (from [Module 2](02-landed-cost.md)), not today's FX.
- Mixed stocked/dropship order → COGS uses each line's actual cost basis (stocked = inventory landed cost; dropship = the cost of the specific PO bought for it).

## Dependencies

- Consumes data from every prior module; this is the read/aggregation layer. Authoritative figures come from [Landed Cost](02-landed-cost.md), [Payments](06-payments.md), and [Returns](07-returns.md).
