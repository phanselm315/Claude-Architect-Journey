# Finance Engineering

I solve finance operating problems for private capital.

For 15 years I worked inside PE-backed finance organizations — Big Four, Northern Trust, fund administration, a Kirkland-adjacent platform — rebuilding the machinery institutional finance actually runs on. I've rebuilt fund accounting. I've rebuilt controllership. I've rebuilt compliance. I've rebuilt reporting. ASC 946 statements, ERP implementations, close processes, audit and custody readiness, distribution waterfalls, LP reporting.

Today AI lets me encode those operating models into software. That's the only reason AI is in this repo at all — it's the newest implementation layer for work I've been doing my whole career, not a new career.

This is the public body of work behind that.

---

## What is Finance Engineering?

Finance engineering sits between finance transformation and software engineering, in the gap neither one closes.

Finance transformation knows *why* a finance organization should work a certain way — where truth should live, what evidence an accounting event needs, who approves what, how a close survives an audit. But it stops at slideware and process maps. It hands the operating model to someone else to build.

Software engineering can build anything, but doesn't carry the operating model. It ships features, not controllership.

A finance engineer designs the operating model **and** encodes it into software. I take the institutional judgment that normally lives in a senior controller's head — the rules, the controls, the "we don't book it until X" — and make it executable, replayable, and auditable.

That's the thing worth building: **institutional memory as software.** Not AI, not agents, not automation for its own sake — institutional judgment, encoded into a system someone can own and trust. The model is rented and commoditizing. The durable asset is the implementation layer around it: the encoded judgment, the domain rules, the checks, the audit trails. Exactly the layer institutional finance has always cared about most.

---

## How I Build

The approach is always the same: **start with the operating model, not the technology.** Why does this process exist? Where does the truth actually live? What evidence and approvals does the accounting event need? **Software comes last** — and only for the parts that should exist at all.

One instinct runs through everything here: output has to be verifiable and hard to silently degrade. That's a controls habit, not an AI one — gates inside gates, human approval before any agent touches the outside world, replayable cores where a discrepancy is always a real signal. That human-approval step does more than catch errors; it's how a person keeps ownership of the system and what it produces, instead of deferring to the model.

The bigger idea sits underneath all of it. Most "company brain" tools build their memory and agents on top of systems that can already be wrong, reconstructing the truth probabilistically — so they end up confidently wrong. Own the reproducible bottom layer instead, and everything above it inherits proof. The same holds for the human layer: the ways of working and hard-won judgment that actually run an organization are usually buried in its knowledge workers — the people who'd benefit most from a system they own and control, rather than one imposed on them.

---

## Selected Work

Three builds carry the thesis. Each runs on synthetic or anonymized data with production-style logic — this is a lab, not a client environment.

### [Forge — AI-Native Fund Accounting ERP](./projects/26-forge-fund-erp/)

**Problem.** Fund administration is built on reconciliation: the same capital activity keyed into four systems, then proven to agree every close. The duplicate sources of truth *are* the cost.

**Approach.** One replayable, deterministic accounting core. ASC 946 statements, distribution waterfalls, and per-class LP reporting are *derived* from it, not reconciled into agreement.

**Result.** Financial statements as evidence, not assertions — the build someone with my background should eventually have made.

### [Portfolio-Company Value-Creation Agents](./projects/20-working-capital-agent/)

**Problem.** Operational-finance diagnostics for portfolio companies die as slides at the end of an engagement. The work isn't reusable and never rolls up to the fund.

**Approach.** Four diagnostics, each pairing a deterministic engine with an LLM judgment layer, each rolling a single-portco win up to a fund-level EBITDA bridge: [Working Capital](./projects/20-working-capital-agent/) (AR / trapped-cash, collections outreach gated behind human approval), [Freight](./projects/21-freight-carrier-optimization-agent/) (shipment history re-priced against live carrier rates), [Inventory](./projects/22-inventory-intelligence-agent/) (ABC × XYZ segmentation, safety/cycle stock, fund-wide pooling MOIC), and [Procurement](./projects/23-procurement-spend-intelligence-agent/) (spend classification, tail/maverick risk, fund-wide negotiation playbook).

**Result.** The diagnostic becomes a reusable fund asset instead of a one-time deliverable.

### [Wacker Advisors OS](./projects/16-wacker-advisors-os/)

**Problem.** A one-person AI-native CFO/CCO practice still has to run compliance calendars, deliverable tracking, and recurring document work without a back office.

**Approach.** The firm's operating model made executable — compliance calendars, deliverable tracking, document automation, with the recurring judgment encoded as rules.

**Result.** Software I run my own practice on. I build what I actually use.

*Browse every build — including earlier and personal projects — in [`projects/`](./projects/).*

---

## Additional Research

Adjacent work — good builds, but supporting evidence rather than the main thesis.

- **[007 — Multi-Agent Equities Research](./projects/17-007-trading-agent/)** — a from-scratch clone of the published *TradingAgents* framework (arXiv [2412.20138](https://arxiv.org/abs/2412.20138)) on the native Anthropic SDK: ~10 agents argue each call, an independent risk agent can veto it. Separation of duties as design.
- **[Kalshi Calibration Study](./projects/06-kalshi-trading/)** — re-ran a published trading-strategy paper on the latest model across 1,274 markets to test whether a stronger model changed the result. It didn't; the markets are well-calibrated. Reporting the negative is the whole discipline.
- **[Sass Factory — a Gated Software Factory](./projects/28-sass-factory/)** — a build loop where nothing merges until it's proven: coding agents in isolated git clones, every change gated at the merge boundary by deterministic checks plus an adversarial review agent. The separation-of-duties instinct of a finance close, turned into a ma