# Inventory Intelligence Agent

**Status:** 🔄 Active  
**Started:** May 2026  
**Repo:** [github.com/phanselm315/inventory-intelligence-agent](https://github.com/phanselm315/inventory-intelligence-agent)  

## What This Is

An AI agent that surfaces the EBITDA — and the cash — trapped inside a mid-market
distributor's inventory. Point it at an inventory snapshot and 24 months of demand
history; it segments the catalog by ABC × XYZ, sizes variability-driven safety stock and
EOQ-rounded cycle stock, surfaces the dead SKUs and the long tail no one's flagged, and
rolls the result into a board-ready EBITDA bridge — for one portfolio company, then
across the fund. Built as a portfolio-company value-creation demo; all data is synthetic
— same fictional fund (Hadrian Capital Partners) as the Working Capital, Freight, and
Procurement agents.

## Architecture

The agent works in two parts:

- **Part 1 — Single-portco diagnostic.** Builds the TTM item master, runs per-SKU demand
  forecasts validated against a hold-out, segments the catalog 3×3 by ABC × XYZ with a
  per-cell service-level target, computes variability-driven safety stock and EOQ-rounded
  cycle stock, and decomposes savings lever by lever — safety stock right-sizing, cycle
  stock / EOQ, SKU rationalization, and obsolescence reserve correction. Rolls into an
  EBITDA bridge with downside / base / upside flow-through, a sensitivity table, and a
  vendor stock-policy playbook.
- **Part 2 — Portfolio rollup.** Re-runs the diagnostic across six inventory-intensive
  fund portcos (the freight/logistics portco is excluded — a freight business carries
  cargo, not inventory). Builds a unified canonical-SKU map across portcos and applies
  cross-portco safety-stock pooling using the classical √N bound, then rolls everything
  into a fund-level EBITDA + enterprise-value bridge — each company held at its own
  entry multiple, no multiple expansion.

Deterministic analytics throughout — every figure traces to an inventory row and
explicit arithmetic. The LLM is used at one step: writing the vendor stock-policy and
SKU-rationalization commentary. Python; a Streamlit app, a Jupyter walkthrough, and a
CLI runner share one `src/`; Plotly for visualization. Mock mode runs offline and
byte-identical; the real API is touched only by the one-time seed script.

## Key Decisions

**Forecast error, not in-sample residuals.** Safety stock is sized off the standard
deviation of forecast error against a hold-out, not against the model's own residuals.
The forecast can lie to itself; the hold-out can't.

**ABC × XYZ over a flat days-of-cover rule.** A flat "two weeks of cover" rule is what
real inventory planning replaces. Segmenting by COGS contribution and demand variability
lets the service-level target reflect what each segment needs — AX at 99%, CZ at
85%, the rest interpolated.

**√N pooling math, capped at realistic capture.** Classical pooling theory says holding
shared safety stock at one fund-level node releases (1 − 1/√N) of the redundant SS across
N portcos. The 8% / 15% / 22% tiers reflect the share of that theoretical maximum a real
pooling program lands — not what the math allows in a vacuum.

**Cross-agent guardrails written in.** Vendor unit-cost reduction is owned by the
Procurement Agent. Inbound freight is owned by the Freight Agent. DSO is owned by the
Working Capital Agent; this agent owns DIO. The boundaries are flagged as explicit config
constants so nothing double-counts at the suite level.

## Lessons Learned

The most useful inventory work is the part that pulls cash off the balance sheet, not
the part that trims a percent of carrying cost. The working-capital release shows up on
the bank statement; the carrying-cost saving shows up in a footnote. Both go in the
bridge — the cash release is what makes the case.

Suite-level guardrails matter as much as in-portco math. Once an inventory agent, a
procurement agent, and a freight agent all touch the same fund, the question becomes who
owns what dollar. Explicit cross-agent boundaries are how the suite stays additive
instead of triple-counting.

Sibling to the [Working Capital Agent](../20-working-capital-agent/) (Project 20), the
[Freight Carrier Optimization Agent](../21-freight-carrier-optimization-agent/) (Project 21),
and the [Procurement Spend Intelligence Agent](../23-procurement-spend-intelligence-agent/)
(Project 23) — the four-agent suite covers the cash conversion cycle and the largest
controllable cost lines in a PE portfolio.

---

*Part of the [Claude Architect Journey](../../README.md)*
