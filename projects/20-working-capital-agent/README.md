# Working Capital Agent

**Status:** 🔄 Active  
**Started:** May 22, 2026  
**Repo:** [github.com/phanselm315/working-capital-agent](https://github.com/phanselm315/working-capital-agent)  

## What This Is

An agentic AI that runs the accounts-receivable diagnostic and collections workflow a
turnaround consultant is hired to do — in seconds, and re-runnable across an entire
private-equity portfolio. Point it at an AR aging file; it returns a CFO-grade diagnostic
of where cash is trapped, sizes the recoverable opportunity, segments the customer book,
and drafts the week's collection outreach — one tone-matched email per account. Built as a
portfolio-company value-creation demo; all data is synthetic.

## Architecture

The pipeline runs in three "acts":

- **Act 1 — Diagnostic.** Deterministic analytics: DSO vs. a realistic target, the full
  aging curve, customer concentration, disputed exposure, and a triangulated
  recoverable-cash opportunity. Claude then writes the board-ready narrative.
- **Act 2 — Remediation loop.** Rules-based customer segmentation, a priority-ranked
  collector worklist, and a Claude-drafted, tone-matched collection email for every
  account — warm for a strategic anchor, firm for a 90-day account, dispute-first where an
  invoice is contested.
- **Act 3 — Treasury rollup.** Re-runs the diagnostic across the whole fund into a single
  value bridge — recurring EBITDA lift, enterprise value at entry multiples, and an
  implied MOIC lift.

An **approval queue** sits between the agent and the outside world: every drafted email is
reviewed and approved by a person before it can send. All arithmetic is deterministic and
auditable — the LLM is used only where language and judgment are the point. Python; a
Streamlit dashboard plus a CLI; demo mode runs fully offline on cached responses, live
mode calls the Anthropic API.

## Key Decisions

**Keep the math out of the model.** Every number traces to an explicit calculation, never
to an LLM — auditable line by line. The model writes prose and judgment calls, not figures.

**The human keeps the send button.** The agent does the work; a person keeps the judgment.
Nothing is sendable until someone signs off.

**Build for the portfolio, not one company.** The treasury rollup is the point — a one-off
cost cut becomes a repeatable, fund-level value-creation lever.

**Synthetic, but production-grade.** A fictional fund and synthetic data, but the input
CSVs deliberately mirror what NetSuite, QuickBooks, or Sage export — pointing the
agent at a real company is a column-mapping exercise, not a rebuild.

## Lessons Learned

The deterministic-vs-LLM boundary is a design decision, not an afterthought. Drawing it
explicitly — arithmetic stays deterministic, language goes to the model — is exactly what
makes the output trustworthy to a finance reader who will check the numbers.

A diagnostic is only half the job. The value is in the standing process — re-run it on
every aging refresh and a one-time consulting deck becomes an always-on collections
workflow.

Sibling to the [Freight Carrier Optimization Agent](../21-freight-carrier-optimization-agent/)
(Project 21), [Inventory Intelligence Agent](../22-inventory-intelligence-agent/)
(Project 22), and [Procurement Spend Intelligence Agent](../23-procurement-spend-intelligence-agent/)
(Project 23) — the four-agent suite covers the cash conversion cycle and the largest
controllable cost lines in a PE portfolio.

---

*Part of the [Claude Architect Journey](../../README.md)*
