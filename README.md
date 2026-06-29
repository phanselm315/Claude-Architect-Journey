# AI Architect Journey
I design, build, and deploy AI systems (production tools, automated workflows, and
multi-agent pipelines) — primarily on the Claude API, and increasingly multi-model. This
is the public record of how I got here.

Inspired by [@cyrilXBT's roadmap](https://x.com/cyrilXBT). Tracked with projects,
milestones, and weekly notes.

---

## Who I Am
CPA and finance transformation leader with 15+ years in private equity and hedge fund operations — focused on process optimization, systems implementation, and controls. I've led large-scale platform migrations and built scalable operations, reporting, and compliance infrastructure for thousands of funds, from small middle market PE firms to the largest alternative asset managers in the world. Notre Dame (Mendoza) BBA/MSA; Illinois CPA.

The moment this clicked for me was watching a broken, manual
finance process get re-architected into something designed, automated, and provable. My
finance and accounting work taught me to treat broken processes as design problems rather than things to
work around, and that instinct carried over when I started building with AI: most of what
I've made since March turns manual, error-prone, or opaque work into something with clearer
inputs, explicit checks, and reviewable outputs.

This is the intersection the whole portfolio is built on: the rigor I brought to reliable,
auditable financial systems, now applied to designing production AI architectures —
agentic workflows with built-in controls, evals, human oversight, and audit trails, for
reporting, compliance, FP&A, and portfolio operations. The bet is that the durable edge in
AI isn't the model; it's the implementation layer and the proof around it.

**Starting point:** Basic Python; no prior API or agent experience  
**Domain:** Finance, compliance, private-equity value creation, nonprofit ops, household automation, and trading  
**Goal:** Over 6 months, build a portfolio that shows what's possible when you use AI
as an actual engineering partner, not a chatbot. Document the work publicly.

---

## Why This Exists
The gap between hobbyists and people earning income from AI is architecture: how to design systems that are reliable, useful, and shippable. This is my public commitment to closing that gap.

**Rules I'm following:**
- Build every single week. No reading-only weeks.
- Ship publicly. Every project gets a README and a demo.
- Use Claude to build with Claude.

---

## How My Workflow Has Changed

My workflow has shifted as I've tried to make AI do real work instead of just generating
text. Early on I was copy-pasting prompts that I worked on in Grok, Claude, or Chat GPT and fixing the output by hand. Then I started letting Claude edit code directly. After that I began handing off bigger tasks to agents that could plan and iterate on their own.

More recently I've been building more structure around the agents: having them review each
other's work (the 007 trading debate, Forge's adversarial reviewers), gating build loops
behind explicit checks, and — most recently — a setup that spins up isolated coding agents
and gates their changes before anything merges. That last one is the current experiment I'm
calling [Sass Factory](./projects/28-sass-factory/). It isn't a new
paradigm; it's just the latest attempt to stop being the bottleneck on every change.

### Where This Is Headed

I'm still figuring out what actually compounds. So far the pattern that seems most valuable
isn't better prompts or even better agents — it's building environments where the output is
easy to verify and hard to silently degrade. The more I try to productionize this work, the
more the job shifts from steering every step myself to designing the checks and handoffs
that keep the system honest — and the bottleneck moves from "can the model do it" to "can I
trust what it just did without re-checking everything myself."

What seems to actually compound isn't the model — it's the implementation layer I build
around it: the encoded judgment, the checks, the domain rules, and the reusable scaffolding
that accumulate with every project. The model is rented and commoditizing; that accumulated
implementation is the part I own. The bet for the business is to capture that moat while
building — turning each engagement's verification logic and domain knowledge into reusable
assets — so every build starts ahead of the last one instead of from scratch, and the
advantage compounds.

I'm not claiming this is a novel insight — plenty of people are converging on similar ideas.
I'm just documenting what the work has actually felt like on the ground.

---

## Roadmap

| Month | Focus                                                                       | Milestone                                                        |
|-------|-----------------------------------------------------------------------------|------------------------------------------------------------------|
| 1     | **Foundation**: prompt engineering, first API calls, daily tools            | First working API script + system prompt library                 |
| 2     | **Master the API**: CLI tools, PDF automation, eval frameworks              | 3 production CLI tools in active use                             |
| 3     | **Tools & Agents**: web scraping, external APIs, data pipelines             | Scraper-agent + parish bookkeeping system         |
| 4     | **Real Products** *(current — June 2026)*: apps used by real people in real life                    | Family Flow App + Wacker Advisors OS + four-agent PE value-creation suite + Forge fund-accounting ERP |
| 5     | **Advanced Architecture**: multi-agent, ML training, trading systems        | 007 paper-trading run · Kalshi calibration study               |
| 6     | **Reputation & Income**: portfolio, outreach, first paid project            | First paid Claude build + public portfolio                       |

> **Note:** Month 3 work includes early builds of roadmap Months 4 & 5. Family Flow, Wacker Advisors OS, the 007 Trading Agent, Kalshi, and a four-agent portfolio-company value-creation suite are all running ahead of schedule.

---

## Finance & PE Applications

The work most directly tied to my domain — fund accounting, PE and asset-management
operations, compliance, and trading. If you came here from finance or PE, start here; the
full chronological index follows below.

| Project | What it is |
|---------|------------|
| [Forge — AI-Native Fund Accounting ERP](./projects/26-forge-fund-erp/) | From-scratch fund-administration platform with an audit-grade, replayable accounting core that reproduces byte-identical. ASC 946 statements, distribution waterfalls, per-class LP reporting — built via gated Claude Code phases and adversarial multi-agent review. |
| [PortCo Value-Creation Agent Suite](#portco-value-creation-agents) | Four PE portfolio-company agents — working capital, freight, inventory, procurement. Each pairs a deterministic diagnostic with an LLM judgment layer; the working-capital agent gates Claude-drafted outreach behind a human approval queue. Single-portco wins roll up to a fund-level EBITDA bridge (MOIC in the inventory agent). |
| [Wacker Advisors OS](./projects/16-wacker-advisors-os/) | The operating system for an AI-native fractional CFO + CCO practice: compliance calendars, deliverable tracking, and document automation. Built and ready to deploy on client engagements. |
| [007 Trading Agent](./projects/17-007-trading-agent/) | Multi-agent equities system: ~10 agents ingest data, debate each trade, and clear it against an independent risk veto. Built to produce a paper-trading research record. |
| [Kalshi Calibration Study](./projects/06-kalshi-trading/) | Academic question → trading bot → research finding (draft prepared for SSRN): BTC daily binaries are well-calibrated with no directional edge. An honest negative result, treated as the product. |
| [Business Prompt Library](./projects/04-business-prompt-library/) | Production Claude skills for CFO/CCO advisory, SEC private-fund compliance, and ASC 946 investment-company accounting. |
| [Monthly Financials Builder](./projects/09-monthly-financials-builder/) | Python CLI that assembles the full monthly board financial package — cover page, donations, expenses, bank statements — from raw QuickBooks Online exports in one command. In monthly use for a nonprofit board. |
| [Parish Bookkeeping System](./projects/11-parish-bookkeeping-system/) | Documented 30 years of undocumented month-end process and automated QuickBooks Online workflows across multiple entities — two churches, a school, and ministries. |

### PortCo Value Creation Agents

Four agents shipped as one body of work (May 2026): a private-equity portfolio-company
value-creation suite. Each runs a deterministic diagnostic on one operational lever, uses
Claude for the judgment layer, and rolls a single-portco win up to a fund-level EBITDA
bridge (MOIC in the inventory agent). On synthetic data with production-style logic; most
are public on GitHub.

| #  | Project                         | Month | Description                                                                                                                    | Started      |
|----|---------------------------------|-------|--------------------------------------------------------------------------------------------------------------------------------|--------------|
| 20 | [Working Capital Agent](./projects/20-working-capital-agent/)           | 3–4   | Agentic accounts-receivable diagnostic + collections tool for PE portfolios: deterministic trapped-cash analysis, customer segmentation, Claude-drafted collection emails behind a human approval queue, and a fund-level treasury rollup | May 22, 2026 |
| 21 | [Freight Carrier Optimization Agent](./projects/21-freight-carrier-optimization-agent/) | 3–4 | Agent that re-prices a manufacturer's shipment history against live carrier rates, decomposes freight savings lever by lever, and rolls a single-portco EBITDA bridge up to a fund-level value-creation play | May 22, 2026 |
| 22 | [Inventory Intelligence Agent](./projects/22-inventory-intelligence-agent/) | 3–4 | Agent that segments a distributor's catalog by ABC × XYZ, sizes variability-driven safety stock and EOQ cycle stock, surfaces dead SKUs and the long tail, and rolls a single-portco working-capital release up to a fund-wide √N pooling play | May 2026     |
| 23 | [Procurement Spend Intelligence Agent](./projects/23-procurement-spend-intelligence-agent/) | 3–4 | Agent that cleans the vendor master, classifies spend by category, surfaces tail / maverick / concentration risk, and rolls per-portco procurement savings up to a fund-wide negotiation playbook | May 2026     |

---

## Project Index

The full chronological list — every build, in order, kept for transparency.

| #  | Project                         | Month | Description                                                                                                                    | Started      |
|----|---------------------------------|-------|--------------------------------------------------------------------------------------------------------------------------------|--------------|
| 01 | [Tax Prep with Claude](./projects/01-tax-prep-with-claude/)             | 2     | Used Claude alongside Free Tax USA to work through a full personal tax filing. First high-stakes real-world AI use             | Apr 2026     |
| 02 | [First API Call](./projects/02-first-api-call/)                         | 1     | Node.js script making a live Claude API call. The foundational proof of concept                                                | Mar 9, 2026  |
| 03 | [Municipal Meeting Scanner](./projects/03-municipal-meeting-scanner/)   | 1–2   | Node.js + Playwright + Claude API: scrapes ~20 gov websites weekly, extracts housing/zoning items into a formatted HTML report  | Mar 9, 2026  |
| 04 | [Business Prompt Library](./projects/04-business-prompt-library/)       | 1–2   | 6 production Claude skills: CFO/CCO advisory, SEC compliance, investment accounting, email drafting, website copy, resume       | Mar 2026     |
| 05 | [Workforce Housing Analyzer](./projects/05-workforce-housing-analyzer/) | 2     | Iterative Excel + AI parcel analysis tool for Leelanau County land acquisition campaign (v3 → v102+)                           | Mar 2026     |
| 06 | [Kalshi Trading](./projects/06-kalshi-trading/)                         | 2–3   | Academic paper → trading bot → research finding: a paper-trading cohort and a 1,274-market calibration study both showed Kalshi's BTC binaries are well-calibrated with no directional edge. Draft prepared for SSRN submission (June 2026) | Apr 2, 2026  |
| 07 | [Obsidian Second Brain](./projects/07-obsidian-second-brain/)           | 2–3   | Knowledge system on Obsidian, now a working synthesis engine: standardized capture templates (Web Clipper, YouTube transcripts, X/Twitter bookmark ingest) feed Claude-assisted synthesized writing and densely linked maps of content | Apr 13, 2026 |
| 08 | [Aether Advisors](./projects/08-aether-advisors/)                       | 2–3   | AI-powered marketing company build: AI image generation, marketing program design, brand strategy, SEO/GEO audits               | Apr 23, 2026 |
| 09 | [Monthly Financials Builder](./projects/09-monthly-financials-builder/) | 2–3   | Python CLI: auto-assembles board financial package (cover page, donations PDF, expenses, bank statements) from QBO exports      | Apr 23, 2026 |
| 10 | [Email Eval Framework](./projects/10-email-eval-framework/)             | 3     | HTML evaluation system for scoring AI-drafted community emails against strict brand voice rules                                 | Apr 2026     |
| 11 | [Parish Bookkeeping System](./projects/11-parish-bookkeeping-system/)   | 3     | Documenting 30-year undocumented processes, automating QBO workflows for 2 churches + school + ministries, training new hire   | Apr 2026     |
| 12 | [Resume Builder Skill](./projects/12-resume-builder-skill/)             | 3     | Claude skill that ingests any job description and produces a tailored version of a formatted master resume with approved language | May 2, 2026  |
| 14 | [Claude Audit](./projects/14-claude-audit/)                             | 3     | Python script to audit and clean up a computer's file system using AI                                                          | May 7, 2026  |
| 15 | [Family Flow App](./projects/15-family-flow-app/)                       | 3     | Personal app: shared calendar aggregation, grocery store hidden API integration (via Claude Code), financial dashboard, Plaid   | Mar 2026     |
| 16 | [Wacker Advisors OS](./projects/16-wacker-advisors-os/)                 | 3     | Full AI-powered operating system for a one-man outsourced CFO/CCO/COO firm. Every workflow automated or AI-assisted            | Mar 2026     |
| 17 | [007 Trading Agent](./projects/17-007-trading-agent/)                   | 3–5   | Multi-agent equities trading system: a from-scratch clone of the "TradingAgents" framework (Xiao, Sun, Luo & Wang, arXiv:2412.20138). ~10 agents ingest data, debate the call, and clear it against an independent risk veto; ~20 hardening sprints in, paper-trading runs began June 2026 | May 16, 2026 |
| 18 | [Grok Brain Export](./projects/18-grok-brain-export/)                   | 3     | Export and clean Grok AI outputs and conversation history for structured integration into Obsidian second brain                 | May 2026     |
| 24 | [Twitter Stock Research Pipeline](./projects/24-twitter-stock-research/)  | 3–4   | Near-zero-touch pipeline from X bookmarks to a stock-research system: scheduled scrape + AI classification into Obsidian, a 500+-ticker tracker with weekday price refresh (FMP), and on-demand Claude valuation sessions. Now layering trend analysis (crowd vs. street) | May 17, 2026 |
| 25 | [Taste Interview: Voice Profile](./projects/25-taste-interview/)          | 3–4   | 100-question Claude-conducted interview extracting my personal writing voice into a profile any AI writing task can load. Checkpointed, hard-rule tagged, drafting exercises included | May 28, 2026 |
| 26 | [Forge: AI-Native Fund Accounting ERP](./projects/26-forge-fund-erp/)     | 4–5   | From-scratch AI-native fund administration platform: audit-grade, replayable accounting core built via a two-tier Claude workflow (architect sessions → gated Claude Code phases → adversarial multi-agent review) | Jun 3, 2026  |
| 27 | [SBGC CLT — STORM Research Synthesis](./projects/27-sbgc-clt-storm/)       | 3–4   | Test of Stanford's STORM / Co-STORM multi-perspective article generation over a built corpus, used to review a community group's community-land-trust research. First run underdelivered — anchoring on one source doc narrowed the synthesis; rebuild planned | Jun 2026     |
| 28 | [Sass Factory](./projects/28-sass-factory/)                              | 5     | Gated software factory: spawns coding agents in isolated git clones, streams their work live, and gates every change at the merge boundary (deterministic `check-all` + an adversarial review agent that votes merge/block), proposing merges as PRs so nothing merges unchecked. Self-advancing — it drives its own (human-defined) backlog through its gates. The gated build-loop pattern generalized into a reusable system | Jun 25, 2026 |
| 29 | [Content Factory](./projects/29-content-factory/)                        | 4     | Faceless short-form video engine: a five-role pipeline (Orchestrator → Trend Scout → Format Architect → Production Line → Evaluator) with a separate six-agent red-team review, producing a small portfolio of niche accounts, governed by a scorecard locked before any data exists and a weekly kill cycle with binding keep/kill gates. Affiliate-first. Early stage — scaffold built, nothing live yet | Jun 7, 2026  |

---

## Resources
- [Anthropic Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
- [Interactive Prompt Tutorial (GitHub)](https://github.com/anthropics/prompt-eng-interactive-tutorial)
- [Getting Started with the API](https://docs.anthropic.com/en/docs/initial-setup)
- [Tool Use Guide](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview)
- [Anthropic Academy (Skilljar)](https://anthropic.skilljar.com)
- [Building Effective Agents](https://docs.anthropic.com/en/docs/agents-and-tools/overview)

---

## Tools Used
- **Models (LLMs):** Claude — predominant (Haiku for scraping/summarization, Sonnet for reasoning, drafting, agents) · Grok (trading-agent research, brain export) · exploring local + open models (Ollama, Kimi)
- **Languages:** Python · JavaScript / Node.js · TypeScript · SQL · HTML/CSS
- **Databases:** PostgreSQL · SQLite · Supabase
- **Backend:** FastAPI · Uvicorn · SQLAlchemy (async) · Typer (CLI)
- **Frontend:** Next.js · React · Tailwind CSS
- **Infra & quality:** Docker / docker-compose · pytest · mypy (strict) · ruff · Ed25519 signing · GitHub Actions
- **Platforms & tools:** Vercel · Streamlit · GitHub · Claude Code · Cowork · Obsidian + Web Clipper · Jupyter · Excel
- **Interfaces:** REST APIs · MCP servers · custom Claude skills
- **Data & finance APIs:** QuickBooks Online · Plaid · Financial Modeling Prep (MCP) · Kalshi · Alpaca · EasyPost · Warp Freight
- **Key libraries:** `@anthropic-ai/sdk` · Playwright · pandas · numpy · scikit-learn · rapidfuzz · Pydantic · yfinance · openpyxl · ReportLab · pypdf · Plotly

---

## Let's Talk

I'm open to conversations on AI-native finance systems, vertical agent implementations for
private equity and asset management, finance transformation leadership roles, and advisory
work.

[LinkedIn](https://www.linkedin.com/in/peter-c-hanselmann-cpa/) · phanselm315@gmail.com

---

## Weekly Log

A build-every-week record. The detail lives in each project page; this is the cadence.

**Month 1 — Foundation (March 2026)**
- First live Claude API call (a six-line Node.js script); kicked off the Municipal Meeting Scanner the same session.
- Built the Business Prompt Library: six production Claude skills (CFO/COO advisory, SEC compliance, ASC 946 accounting, community email, website copy, resume). Lesson: a structured system prompt with hard rules beats a generic one decisively.

**Month 2 — Master the API (March–April 2026)**
- Municipal Meeting Scanner: Playwright pulls ~20 government sites into a scored housing/zoning report.
- Workforce Housing Analyzer: iterative AI parcel analysis (v102+); extracted county tax-parcel data in minutes versus a $2,500 quote.
- Kalshi Trading begins as an academic question and becomes a BTC paper-trading bot.
- Obsidian Second Brain matures from capture into a Claude-assisted synthesis engine.
- Monthly Financials Builder (QuickBooks board package) and Aether Advisors (marketing-AI infrastructure) launch the same day.
- Email Eval Framework: first structured brand-voice scoring layer.
- Tax Prep with Claude: first high-stakes use — a full personal filing — the experience everything else traces back to.

**Month 3 — Tools & Agents (May 2026)**
- Parish Bookkeeping: stepped in as interim bookkeeper; documented 30 years of undocumented process and automated QuickBooks workflows across multiple entities.
- Resume Builder skill and Claude Audit (AI-assisted file-system cleanup).
- Family Flow App: shared family calendar, grocery APIs reverse-engineered via Claude Code, Plaid spending dashboard.
- Wacker Advisors OS: the full operating system for a one-person CFO/CCO practice.
- Kalshi: the edge didn't hold — a 1,274-market calibration study found no directional edge. The negative result is the finding.
- 007 Trading Agent: a from-scratch multi-agent equities system, ~20 hardening sprints into a paper-trading run.
- PortCo Value-Creation suite — working capital, freight, inventory, procurement — shipped as one body of work.
- Twitter Stock Research pipeline, Grok Brain Export, and the Taste Interview voice profile.

**Month 4 — Real Products (June 2026)**
- Forge (AI-native fund-accounting ERP): eleven gated phases in a few days; an audit-grade, replayable, byte-identical core. Then ASC 946 statements, distribution waterfalls, per-class LP reporting, and byte-exact seed surgery — ~580 tests with adversarial review green.
- Kalshi calibration study written up; draft prepared for SSRN submission.
- Content Factory: a faceless short-form-video engine — a five-role pipeline with a separate six-agent red-team review, locked eval scorecards, and weekly kill-cycle gates.
- Wacker OS built out and ready to deploy on client work; website launch impending.

**Month 5 — Advanced Architecture (June 2026)**
- Sass Factory: the gated-loop pattern generalized into a reusable software factory — gated at the merge boundary, now driving its own (human-defined) backlog through its gates. The most structured of these experiments so far.

**Month 6 — Reputation & Income**
- Underway: this portfolio, outreach, and first paid work.

---

*Started: March 1, 2026 · Updated: June 28, 2026*
