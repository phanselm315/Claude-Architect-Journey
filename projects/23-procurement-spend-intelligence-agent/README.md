# Procurement Spend Intelligence Agent

**Status:** 🔄 Active  
**Started:** May 2026  
**Repo:** [github.com/phanselm315/procurement-spend-intelligence-agent](https://github.com/phanselm315/procurement-spend-intelligence-agent)  

## What This Is

An AI agent that surfaces the EBITDA hiding inside procurement — the largest
controllable cost line in mid-market manufacturing and distribution that almost no one
actively manages. Point it at a portfolio company's AP / invoice export; it cleans the
vendor master, classifies spend into a standard taxonomy, sizes the recoverable
opportunity lever by lever, and rolls the result into a board-ready EBITDA bridge — for
one portfolio company, then across the fund. Built as a portfolio-company
value-creation demo; all data is synthetic — same fictional fund (Hadrian Capital
Partners) as the Working Capital, Freight, and Inventory agents.

## Architecture

The agent works in two parts:

- **Part 1 — Single-portco diagnostic.** Normalizes the vendor master with rapidfuzz +
  light clustering (collapsing alias variants down to canonical suppliers), classifies
  every line into a 10-category taxonomy (rule-based on GL account + description
  keywords), and surfaces the three diagnostics every procurement operator asks for:
  **tail spend**, **maverick spend** (off-PO purchases in contracted categories), and
  **concentration risk**. Savings decompose into four named levers — vendor
  consolidation, category rationalization, payment-terms standardization, and
  contract-coverage uplift — never a single black-box percentage.
- **Part 2 — Portfolio rollup.** Re-runs the diagnostic across seven fund portcos,
  builds a unified fund-wide spend cube (vendor × category × portco), and isolates
  where the real leverage lives: vendors used in three or more portcos with no master
  agreement; categories where pooled volume crosses tier thresholds suppliers
  price against; and payment-terms misalignment costing the fund free working-capital
  financing. Applies a tiered consolidation discount (8% / 15% / 22% for light pooling /
  base / full bloc) and produces a Fund-Wide Negotiation Playbook — a
  category-by-category cheat sheet an operating partner can take into a kickoff meeting
  the next day.

Deterministic analytics throughout — vendor canonicalization, category classification,
and the entire fund rollup all trace to invoices and explicit arithmetic. The LLM is
used at one step: writing the category-level negotiation talking points. Python; a
Streamlit app and a Jupyter walkthrough share one `src/`; Plotly for visualization. Mock
mode runs offline and byte-identical; the real API is touched only by the one-time seed
script.

## Key Decisions

**Vendor canonicalization with a numeric guard.** A two-pass clusterer collapses alias
variants to canonical suppliers — exact-match on a noise-stripped key, then rapidfuzz
`token_set_ratio` above a tunable threshold. A numeric-token guard prevents two vendors
with different account IDs from ever merging on text similarity alone. Precision ≥ 0.99
and recall ≥ 0.96 against the seeded answer key.

**Four named levers, not one black-box percentage.** Vendor consolidation, category
rationalization, payment-terms standardization, contract-coverage uplift — each
opportunity is sized independently. A consultant who can't say where the savings came
from isn't useful; same standard here.

**Contestable-share filter on portfolio leverage.** The tiered discount is scaled by the
share of indirect spend genuinely open to fund-level re-negotiation in a 12–18 month
window (default 40%). The rest is locked into multi-year contracts, specialty-vendor
switching costs, or ad-hoc spend too unstructured to consolidate. Tune the share if a
portfolio-ops team has hard data on portfolio contract coverage.

**Cross-agent guardrails written in.** Shipping & Logistics is owned by the Freight
Agent — shown in the procurement category map but flagged and excluded from the
procurement EBITDA bridge. Payment-terms standardization (AP float) is the payables-side
counterpart to the Working Capital Agent's AR / DSO lever. The boundaries are flagged so
nothing double-counts at the suite level.

## Lessons Learned

The unglamorous lever is often the biggest one. Procurement rarely makes the 100-day
plan's headline; payroll and pricing usually do. Naming it as the largest
*controllable, unmanaged* cost line — before optimizing anything — is the part a
value-creation team hires for.

The fund-level lever is the whole point. A single portco's procurement diagnostic is a
useful piece of consulting work. The same diagnostic run across seven portcos with a
shared vendor pool is a structurally different play — and that's where the math
compounds.

Sibling to the [Working Capital Agent](../20-working-capital-agent/) (Project 20), the
[Freight Carrier Optimization Agent](../21-freight-carrier-optimization-agent/) (Project 21),
and the [Inventory Intelligence Agent](../22-inventory-intelligence-agent/) (Project 22) —
the four-agent suite covers the cash conversion cycle and the largest controllable cost
lines in a PE portfolio.

---

*Part of the [Claude Architect Journey](../../README.md)*
