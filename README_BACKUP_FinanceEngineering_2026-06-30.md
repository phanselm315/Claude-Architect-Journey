# Finance Engineering

Building pieces of the next generation of finance infrastructure for private capital — fund administration, controllership, and portfolio-company value creation.

I've spent 15 years redesigning how institutional finance runs — fund accounting operating models, ERP implementations, controllership and compliance builds across PE, hedge funds, and fund administration. AI and software are just the newest tools for the same job. This repo is where I prototype what AI-native finance systems should look like.

The approach is always the same: start with the operating model, not the technology. Why does this process exist? Where does the truth actually live? What evidence and approvals does the accounting event need? Software comes last — only for the parts that should exist at all.

---

## Selected Work

Most run on synthetic or anonymized data with production-style logic. This is a lab, not a client environment.

**[Forge — AI-Native Fund Accounting ERP](./projects/26-forge-fund-erp/)**
Fund administration is built on reconciliation: the same capital activity keyed into four systems, then proven to agree every close. Forge removes the duplicate sources of truth — one replayable, deterministic accounting core from which ASC 946 statements, distribution waterfalls, and per-class LP reporting are *derived*, not reconciled. Financial statements as evidence, not assertions.

**Portfolio-Company Value-Creation Agents**
Four operational-finance diagnostics, each pairing a deterministic engine with an LLM judgment layer, each rolling a single-portco win up to a fund-level EBITDA bridge. The value-creation diagnostic becomes a reusable asset instead of a slide that dies with the engagement.

- **[Working Capital](./projects/20-working-capital-agent/)** — agentic AR diagnostic and collections tool: trapped-cash analysis, customer segmentation, Claude-drafted outreach gated behind a human approval queue, fund-level treasury rollup.
- **[Freight](./projects/21-freight-carrier-optimization-agent/)** — re-prices a manufacturer's shipment history against live carrier rates and decomposes the savings lever by lever into an EBITDA bridge.
- **[Inventory](./projects/22-inventory-intelligence-agent/)** — segments a distributor's catalog by ABC × XYZ, sizes safety stock and EOQ cycle stock, surfaces dead SKUs, and rolls a working-capital release up to a fund-wide √N pooling play (MOIC).
- **[Procurement](./projects/23-procurement-spend-intelligence-agent/)** — cleans the vendor master, classifies spend, surfaces tail / maverick / concentration risk, and rolls per-portco savings up to a fund-wide negotiation playbook.

**[Wacker Advisors OS](./projects/16-wacker-advisors-os/)**
The operating system for a one-person AI-native CFO/CCO practice — compliance calendars, deliverable tracking, document automation, with the recurring judgment encoded as rules. The firm's operating model, made executable.

**[007 — Multi-Agent Equities Research](./projects/17-007-trading-agent/)**
A working clone of the published *TradingAgents: Multi-Agents LLM Financial Trading Framework* (arXiv [2412.20138](https://arxiv.org/abs/2412.20138)), rebuilt from scratch on the native Anthropic SDK: ~10 agents argue each call and an independent risk agent can veto it. Separation of duties as design — the same reason finance splits who approves from who executes. Produces a paper-trading research record.

**[Kalshi Calibration Study](./projects/06-kalshi-trading/)**
Took a published trading-strategy paper, re-ran its methodology on the latest model, and backtested to see whether a stronger model changed the result — a 1,274-market study. It didn't: the markets are well-calibrated, with no directional edge. Written up as an academic paper. The willingness to test the claim and report the negative is the whole discipline — in trading and in controllership.

**[Sass Factory — a Gated Software Factory](./projects/28-sass-factory/)**
A build loop where work can't merge until it's proven. It spawns coding agents in isolated git clones, streams their work live, and gates every change at the merge boundary — deterministic checks plus an adversarial review agent that votes merge or block — so nothing lands unchecked. Then it closes the loop on itself: it drives its own backlog through its own gates, a loop of loops where the factory advances the work and the gates keep it honest. The same separation-of-duties and audit-trail instinct that governs a finance close, turned into a machine that builds.

*Browse every build — including the earlier and personal projects — in [`projects/`](./projects/).*

---

## Engineering for Trust

One instinct runs through all of it: output has to be verifiable and hard to silently degrade. That's a controls habit, not an AI one — gates inside gates, human approval before any agent touches the outside world, replayable cores where a discrepancy is always a real signal. And in my experience, that human-approval step does more than catch errors — it's how a person keeps ownership of the system and what it produces, instead of deferring to the model.

The model is rented and commoditizing. The durable asset is the implementation layer around it — the encoded judgment, domain rules, checks, and audit trails. Exactly the layer institutional finance has always cared about most.

The bigger idea sits underneath all of it. Most "company brain" tools build their memory and agents on top of systems that can already be wrong, reconstructing the truth probabilistically — so they end up confidently wrong. Own the reproducible bottom layer instead, and everything above it inherits proof. The same holds for the human layer: the ways of working, institutional judgment, and hard-won knowledge that actually run an organization are often buried in its knowledge workers — the people who'd benefit most from a system they could own, manage, and control, rather than one imposed on them.

---

## Stack

Python · TypeScript · FastAPI · async SQLAlchemy · PostgreSQL · Next.js / React. Claude as the primary model (Haiku for extraction, Sonnet for reasoning and agents); Grok and local models in the mix. Controls-grade hygiene: pytest, strict mypy, Docker, signed artifacts, CI gates, custom MCP servers and Claude skills. Finance plumbing through QuickBooks Online, Plaid, and Financial Modeling Prep.

The full chronological record of every build — including the early and personal projects — is in [`LOG.md`](./LOG.md).

---

## Let's Talk

I'm open to conversations on AI-native finance systems, vertical agent implementations for private equity and asset management, finance transformation leadership roles, and advisory work.

[LinkedIn](https://www.linkedin.com/in/peter-c-hanselmann-cpa/) · phanselm315@gmail.com
