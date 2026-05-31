# Freight Carrier Optimization Agent

**Status:** 🔄 Active  
**Started:** May 22, 2026  
**Repo:** [github.com/phanselm315/freight-carrier-optimization-agent](https://github.com/phanselm315/freight-carrier-optimization-agent)  

## What This Is

An AI agent that surfaces the EBITDA hiding inside freight — one of the last unmanaged
cost lines in the mid-market. Point it at a manufacturer's twelve-month shipment history;
it re-prices every shipment against live carrier rates, isolates the savings lever by
lever, and turns the result into a board-ready EBITDA bridge — for one portfolio company,
then across an entire fund. Built as a portfolio-company value-creation demo; all data is
synthetic — a fictional injection molder inside a fictional PE fund.

## Architecture

The agent works in two parts:

- **Part 1 — Single-portco diagnostic.** Re-prices every shipment against live carrier
  rates — parcel through EasyPost, LTL through Warp Freight — and benchmarks each against
  what unmanaged, plant-by-plant booking paid. Savings are decomposed lever by
  lever: carrier mix, mode selection, shipment consolidation, and expedited-freight
  reduction. The result rolls into an EBITDA bridge with downside / base / upside
  flow-through, a sensitivity table, and a one-page carrier negotiation scorecard.
- **Part 2 — Portfolio rollup.** Re-runs the diagnostic across four freight-intensive fund
  portfolio companies and applies a tiered portfolio-leverage discount, rolling into a
  fund-level EBITDA and enterprise-value bridge — each company held at its own entry
  multiple.

The analytics are fully deterministic — every figure traces to a rate lookup and explicit
arithmetic. The LLM is used at exactly one step: turning the analysis into the negotiation
scorecard's talking points. Python; a Streamlit app and a Jupyter walkthrough share one
`src/` so the demo and the deep-dive can't drift apart; Plotly for visualization. Mock
mode runs offline and byte-identical; the real carrier APIs are touched only when caches
are explicitly rebuilt.

## Key Decisions

**Find the lever, not just the savings.** Freight is a ~5% cost line most diligence skims
past. The demo opens by *identifying* it as the largest controllable, unmanaged cost —
before optimizing anything. Knowing where margin hides is the judgment a value-creation
team hires for.

**Speak the value-creation plan's language.** The output isn't "savings" — it's an EBITDA
bridge with downside / base / upside flow-through and enterprise value held at the entry
multiple, no multiple expansion. It's structured the way a deal team and a board expect to
receive it.

**Every assumption stated and tunable.** Real carrier rates are flagged separately from
modeled fallbacks; the status-quo inefficiency premium — the single largest assumption —
is one named, tunable parameter. The analysis is built to survive scrutiny from someone
who does this for a living.

**Reproducible by default.** A seeded synthetic data generator plus cached rates produce
identical results offline, every run.

## Lessons Learned

The judgment is in finding the cost line, not optimizing it. Re-pricing shipments is
arithmetic; recognizing that freight is the largest *controllable* cost no one owns is the
actual work.

Deterministic math with a narrow, single-purpose LLM layer is the trustworthy shape for a
finance tool — the same boundary that makes the
[Working Capital Agent](../20-working-capital-agent/) (Project 20),
[Inventory Intelligence Agent](../22-inventory-intelligence-agent/) (Project 22), and
[Procurement Spend Intelligence Agent](../23-procurement-spend-intelligence-agent/) (Project 23)
credible. Together, the four agents cover the cash conversion cycle and the largest
controllable cost lines in a PE portfolio.

---

*Part of the [Claude Architect Journey](../../README.md)*
