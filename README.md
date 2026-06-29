# AI Architect Journey
I design, build, and deploy AI systems (production tools, automated workflows, and
multi-agent pipelines) — primarily on the Claude API, and increasingly multi-model. This
is the public record of how I got here.

Inspired by [@cyrilXBT's roadmap](https://x.com/cyrilXBT). Tracked with projects,
milestones, and weekly notes.

---

## Who I Am
CPA and finance transformation leader with 15+ years in private equity and hedge fund
operations — focused on process optimization, systems implementation, and controls. I've
led large-scale platform migrations and built scalable reporting and compliance
infrastructure for hundreds of funds, including a ~$9M operations platform migration that
cut manual effort ~70% and saved ~$8M, and the operational stand-up behind a $150M fund
launch. Notre Dame (Mendoza) BBA/MSA; Illinois CPA.

The moment this clicked for me wasn't a model demo. It was watching a broken, manual
finance process get re-architected into something designed, automated, and provable — and
realizing how much leverage lives in the *system around the work*, not the work itself.
That same feeling (*the world just changed and I need to master it*) is what hit me when I
started building seriously with AI. I'm relentless about delivering for the people who
depend on me, and I won't leave a broken process alone — and now I have both the domain
expertise and the tools to build the fix.

This is the intersection the whole portfolio is built on: the rigor I brought to reliable,
auditable financial systems, now applied to designing production AI architectures —
agentic workflows with built-in controls, evals, human oversight, and audit trails, for
reporting, compliance, FP&A, and portfolio operations. The bet is that the durable edge in
AI isn't the model; it's the implementation layer and the proof around it.

---

## Why This Exists
The gap between hobbyists and people earning income from AI is architecture: how to design systems that are reliable, useful, and shippable. This is my public commitment to closing that gap.

**Rules I'm following:**
- Build every single week. No reading-only weeks.
- Ship publicly. Every project gets a README and a demo.
- Use Claude to build with Claude (yes, it's meta).

---

## The Arc

The projects below are the *what*. This is the *how* — and it's the part that actually
compounded. Over six months my unit of work kept moving up a level of abstraction:

1. **Copy-pasting prompts.** One prompt, one answer, into the chat box. My voice and my
   context lived in my head and got retyped every time.
2. **Into Claude Code.** Stopped pasting and let Claude touch the codebase directly. The
   loop tightened from "ask, paste, fix" to "describe, review, ship."
3. **Into a single agent.** Handed off a whole task to an agent that planned and executed
   on its own, instead of me steering every step.
4. **Into multi-agent orchestration.** Agents that argue opposite sides, review each
   other, and clear work against an independent veto — the 007 trading debate, Forge's
   adversarial reviewers tasked with proving the build dishonest.
5. **Into agent loops.** Gated, self-checking build loops: a versioned phase prompt feeds
   Claude Code, which implements behind hard stop conditions, which feeds a review pass
   that either passes or kicks it back. Progress stops being vibes.
6. **Into loops of loops.** Where the AI-native ERP build (Forge) actually lives — nested
   loops where the *process* of building is itself an orchestrated system, not a person
   running a checklist.
7. **Into a factory.** The loops-of-loops extracted from a single build and made a reusable
   system — [Sass Factory](./projects/28-sass-factory/) (Project 28). Sandboxed agents
   spawned at a repo, watched live, with every change gated at the merge boundary:
   deterministic checks plus an adversarial reviewer that votes merge or block, so nothing
   ships unchecked. It now advances its own backlog with no human shuttling prompts between
   sessions. The build process stopped being something I run and became something I *own*:
   a factory that builds, reviews, tests, and ships software end to end — and is currently
   building itself.

The shift that ties it together: I've stopped being the loop *operator* and become the loop
*designer*. The job isn't to run loops faster — it's to decide which loops exist, what each
one is for, and how they hand off; then to monitor them as they run and tweak the ones that
drift; and to keep the context they run against clean enough that each run leaves the next
one better. A planned portfolio of loops I design, watch, and tune — not a bag of tricks.

That meta move is no longer aspirational — it's built. The reusable **AI engineering team**
is **Sass Factory**: every lesson from the Forge build and from my own machine setup,
synthesized into a gated, self-advancing software factory. It's already dogfooding —
building its own backlog through its own control plane and gate chain — and the next move is
simply pointing it at the next product. Lessons stopped being trapped inside one build and
started compounding across all of them. That was always the thesis: not "I used AI to build
a thing," but "I built the system that builds the things, and it gets better every cycle."
Now it exists.

### Where This Is Headed

*My read of the tea leaves — light, and held loosely.*

The leverage is moving off the model and onto the **system around it**. Models are becoming a
commodity input; everyone will have a good one. The durable edge is the implementation layer
— the workflow design, the authority limits, the evals and audit trails — wrapped around a
context store that gets richer every cycle instead of sitting still. Three things I keep
betting on: the unit of work has climbed from the prompt to a designed portfolio of loops,
and the scarce skill is now designing and tuning them, not running them; the moat isn't
intelligence but the compounding context and judgment you've encoded into the system — the
part that doesn't commoditize when the model does; and proof is the product — you stop
trusting the agent and start trusting the environment around it, building the verification
so failure is hard and the quality floor only ratchets up; "done isn't done" until the
output is provable, not merely plausible. That's the entire reason Forge exists. Put it together and the people who win this next phase are the ones who can turn
their own expertise into a system that runs without them — and prove it was right. That's the
bet the whole portfolio is built on, and where I think everything is going.

---

## Roadmap

| Month | Focus                                                                       | Milestone                                                        | Status |
|-------|-----------------------------------------------------------------------------|------------------------------------------------------------------|--------|
| 1     | **Foundation**: prompt engineering, first API calls, daily tools            | First working API script + system prompt library                 | ✅      |
| 2     | **Master the API**: CLI tools, PDF automation, eval frameworks              | 3 production CLI tools in active use                             | ✅      |
| 3     | **Tools & Agents**: web scraping, external APIs, data pipelines             | Scraper-agent + parish bookkeeping system + fraud finder         | 🔄      |
| 4     | **Real Products**: apps used by real people in real life                    | Family Flow App + Wacker Advisors OS + four-agent PE value-creation suite + Forge fund-accounting ERP | 🔄 ← Current (June 2026) |
| 5     | **Advanced Architecture**: multi-agent, ML training, trading systems        | 007 agent live paper run · Kalshi calibration study               | 🔄      |
| 6     | **Reputation & Income**: portfolio, outreach, first paid project            | First paid Claude build + public portfolio                       | ⬜      |

> **Note:** Month 3 work includes early builds of roadmap Months 4 & 5. Family Flow, Wacker Advisors OS, the 007 Trading Agent, Kalshi, and a four-agent portfolio-company value-creation suite are all running ahead of schedule.

---

## Finance & PE Applications

The work most directly tied to my domain — fund accounting, PE and asset-management
operations, compliance, and trading. If you came here from finance or PE, start here; the
full chronological index follows below.

| Project | What it is |
|---------|------------|
| [Forge — AI-Native Fund Accounting ERP](./projects/26-forge-fund-erp/) | From-scratch fund-administration platform with an audit-grade, replayable accounting core that reproduces byte-identical. ASC 946 statements, distribution waterfalls, per-class LP reporting — built via gated Claude Code phases and adversarial multi-agent review. |
| [PortCo Value-Creation Agent Suite](#portco-value-creation-agents) | Four PE portfolio-company agents — working capital, freight, inventory, procurement. Each pairs a deterministic diagnostic with an LLM judgment layer behind a human approval queue, rolling a single-portco win up to a fund-level EBITDA / MOIC story. |
| [Wacker Advisors OS](./projects/16-wacker-advisors-os/) | The operating system for an AI-native fractional CFO + CCO practice: compliance calendars, deliverable tracking, and document automation. Now running on live consultancy work. |
| [007 Trading Agent](./projects/17-007-trading-agent/) | Multi-agent equities system: ~10 agents ingest data, debate each trade, and clear it against an independent risk veto. Built to produce a live paper-trading research record. |
| [Kalshi Calibration Study](./projects/06-kalshi-trading/) | Academic question → live trading bot → published SSRN finding: BTC daily binaries are well-calibrated with no directional edge. An honest negative result, treated as the product. |
| [Business Prompt Library](./projects/04-business-prompt-library/) | Production Claude skills for CFO/CCO advisory, SEC private-fund compliance, and ASC 946 investment-company accounting. |

---

## Project Index

The full chronological list — every build, in order, kept for transparency.

| #  | Project                         | Month | Description                                                                                                                    | Started      | Status    |
|----|---------------------------------|-------|--------------------------------------------------------------------------------------------------------------------------------|--------------|-----------|
| 01 | [Tax Prep with Claude](./projects/01-tax-prep-with-claude/)             | 2     | Used Claude alongside Free Tax USA to work through a full personal tax filing. First high-stakes real-world AI use             | Apr 2026     | ✅ Done    |
| 02 | [First API Call](./projects/02-first-api-call/)                         | 1     | Node.js script making a live Claude API call. The foundational proof of concept                                                | Mar 9, 2026  | ✅ Done    |
| 03 | [Municipal Meeting Scanner](./projects/03-municipal-meeting-scanner/)   | 1–2   | Node.js + Playwright + Claude API: scrapes ~20 gov websites weekly, extracts housing/zoning items into a formatted HTML report  | Mar 9, 2026  | ✅ Done    |
| 04 | [Business Prompt Library](./projects/04-business-prompt-library/)       | 1–2   | 6 production Claude skills: CFO/CCO advisory, SEC compliance, investment accounting, email drafting, website copy, resume       | Mar 2026     | ✅ Done    |
| 05 | [Workforce Housing Analyzer](./projects/05-workforce-housing-analyzer/) | 2     | Iterative Excel + AI parcel analysis tool for Leelanau County land acquisition campaign (v3 → v102+)                           | Mar 2026     | 🔄 Active  |
| 06 | [Kalshi Trading](./projects/06-kalshi-trading/)                         | 2–3   | Academic paper → trading bot → research finding: live paper-trading and a 1,274-market calibration study showed Kalshi's BTC binaries are well-calibrated with no directional edge. Result published on SSRN (June 2026) | Apr 2, 2026  | ✅ Done    |
| 07 | [Obsidian Second Brain](./projects/07-obsidian-second-brain/)           | 2–3   | Knowledge system on Obsidian, now a working synthesis engine: standardized capture templates (Web Clipper, YouTube transcripts, X/Twitter bookmark ingest) feed Claude-assisted synthesized writing and densely linked maps of content | Apr 13, 2026 | 🔄 Active  |
| 08 | [Aether Advisors](./projects/08-aether-advisors/)                       | 2–3   | AI-powered marketing company build: AI image generation, marketing program design, brand strategy, SEO/GEO audits               | Apr 23, 2026 | 🔄 Active  |
| 09 | [Monthly Financials Builder](./projects/09-monthly-financials-builder/) | 2–3   | Python CLI: auto-assembles board financial package (cover page, donations PDF, expenses, bank statements) from QBO exports      | Apr 23, 2026 | ✅ Done    |
| 10 | [Email Eval Framework](./projects/10-email-eval-framework/)             | 3     | HTML evaluation system for scoring AI-drafted community emails against strict brand voice rules                                 | Apr 2026     | ✅ Done    |
| 11 | [Parish Bookkeeping System](./projects/11-parish-bookkeeping-system/)   | 3     | Documenting 30-year undocumented processes, automating QBO workflows for 2 churches + school + ministries, training new hire   | Apr 2026     | 🔄 Active  |
| 12 | [Resume Builder Skill](./projects/12-resume-builder-skill/)             | 3     | Claude skill that ingests any job description and produces a tailored version of a formatted master resume with approved language | May 2, 2026  | ✅ Done    |
| 13 | [Fraud Finder](./projects/13-fraud-finder/)                             | 3     | Public-data scraper + agent mapping links between Illinois politicians, newly formed LLCs, and state contract awards            | May 2, 2026  | 🔄 Active  |
| 14 | [Claude Audit](./projects/14-claude-audit/)                             | 3     | Python script to audit and clean up a computer's file system using AI                                                          | May 7, 2026  | ✅ Done    |
| 15 | [Family Flow App](./projects/15-family-flow-app/)                       | 3     | Personal app: shared calendar aggregation, grocery store hidden API integration (via Claude Code), financial dashboard, Plaid   | Mar 2026     | 🔄 Active  |
| 16 | [Wacker Advisors OS](./projects/16-wacker-advisors-os/)                 | 3     | Full AI-powered operating system for a one-man outsourced CFO/CCO/COO firm. Every workflow automated or AI-assisted            | Mar 2026     | 🔄 Active  |
| 17 | [007 Trading Agent](./projects/17-007-trading-agent/)                   | 3–5   | Multi-agent equities trading system: a from-scratch clone of the "TradingAgents" framework (Xiao, Sun, Luo & Wang, arXiv:2412.20138). ~10 agents ingest data, debate the call, and clear it against an independent risk veto; ~20 hardening sprints in, live paper run begins May 26 | May 16, 2026 | 🔄 Active  |
| 18 | [Grok Brain Export](./projects/18-grok-brain-export/)                   | 3     | Export and clean Grok AI outputs and conversation history for structured integration into Obsidian second brain                 | May 2026     | ✅ Done    |
| 24 | [Twitter Stock Research Pipeline](./projects/24-twitter-stock-research/)  | 3–4   | Zero-touch pipeline from X bookmarks to a stock-research system: scheduled scrape + AI classification into Obsidian, a 500+-ticker tracker with weekday price refresh (FMP), and on-demand Claude valuation sessions. Now layering trend analysis (crowd vs. street) | May 17, 2026 | 🔄 Active  |
| 25 | [Taste Interview: Voice Profile](./projects/25-taste-interview/)          | 3–4   | 100-question Claude-conducted interview extracting my personal writing voice into a profile any AI writing task can load. Checkpointed, hard-rule tagged, drafting exercises included | May 28, 2026 | ✅ Done    |
| 26 | [Forge: AI-Native Fund Accounting ERP](./projects/26-forge-fund-erp/)     | 4–5   | From-scratch AI-native fund administration platform: audit-grade, replayable accounting core built via a two-tier Claude workflow (architect sessions → gated Claude Code phases → adversarial multi-agent review) | Jun 3, 2026  | 🔄 Active  |
| 27 | [SBGC CLT — STORM Research Synthesis](./projects/27-sbgc-clt-storm/)       | 3–4   | Test of Stanford's STORM / Co-STORM multi-perspective article generation over a built corpus, used to review a community group's community-land-trust research. First run underdelivered — anchoring on one source doc narrowed the synthesis; rebuild planned | Jun 2026     | 🔄 Active  |
| 28 | [Sass Factory](./projects/28-sass-factory/)                              | 5     | Gated software factory: spawns sandboxed coding agents at a repo, streams their work live, and gates every change at the merge boundary (deterministic `check-all` + an adversarial review agent that votes merge/block) so nothing ships unchecked. Self-advancing — it now builds its own backlog. The Arc's "loops of loops" generalized into a reusable system | Jun 25, 2026 | 🔄 Active  |
| 29 | [Content Factory](./projects/29-content-factory/)                        | 4     | Faceless short-form video engine: a six-agent system (Trend Scout → Format Architect → Production Line → Evaluator) producing a small portfolio of niche accounts, governed by a scorecard locked before any data exists and a weekly kill cycle with binding keep/kill gates. Affiliate-first. Early stage — scaffold built, nothing live yet | Jun 7, 2026  | 🔄 Active  |

### PortCo Value Creation Agents

Four agents shipped as one body of work (May 2026): a private-equity portfolio-company
value-creation suite. Each runs a deterministic diagnostic on one operational lever, uses
Claude for the judgment layer, and rolls a single-portco win up to a fund-level EBITDA and
MOIC story. All public on GitHub, all on synthetic data with production-grade logic.

| #  | Project                         | Month | Description                                                                                                                    | Started      | Status    |
|----|---------------------------------|-------|--------------------------------------------------------------------------------------------------------------------------------|--------------|-----------|
| 20 | [Working Capital Agent](./projects/20-working-capital-agent/)           | 3–4   | Agentic accounts-receivable diagnostic + collections tool for PE portfolios: deterministic trapped-cash analysis, customer segmentation, Claude-drafted collection emails behind a human approval queue, and a fund-level treasury rollup | May 22, 2026 | 🔄 Active  |
| 21 | [Freight Carrier Optimization Agent](./projects/21-freight-carrier-optimization-agent/) | 3–4 | Agent that re-prices a manufacturer's shipment history against live carrier rates, decomposes freight savings lever by lever, and rolls a single-portco EBITDA bridge up to a fund-level value-creation play | May 22, 2026 | 🔄 Active  |
| 22 | [Inventory Intelligence Agent](./projects/22-inventory-intelligence-agent/) | 3–4 | Agent that segments a distributor's catalog by ABC × XYZ, sizes variability-driven safety stock and EOQ cycle stock, surfaces dead SKUs and the long tail, and rolls a single-portco working-capital release up to a fund-wide √N pooling play | May 2026     | 🔄 Active  |
| 23 | [Procurement Spend Intelligence Agent](./projects/23-procurement-spend-intelligence-agent/) | 3–4 | Agent that cleans the vendor master, classifies spend by category, surfaces tail / maverick / concentration risk, and rolls per-portco procurement savings up to a fund-wide negotiation playbook | May 2026     | 🔄 Active  |

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

## About
**Starting point:** Basic Python; no prior API or agent experience  
**Domain:** Finance, compliance, private-equity value creation, nonprofit ops, household automation, and trading  
**Goal:** Over 6 months, build a portfolio that shows what's possible when you use AI
as an actual engineering partner, not a chatbot. Document the work publicly.

---

## Let's Talk

I'm open to conversations on AI-native finance systems, vertical agent implementations for
private equity and asset management, finance transformation leadership roles, and advisory
work.

[LinkedIn](https://www.linkedin.com/in/peter-c-hanselmann-cpa/) · phanselm315@gmail.com

---

## Weekly Log

### Month 1: Foundation (Early–March 2026)

**Week 1 (Mar 9)**
Shipped the first API call: a six-line Node.js script that hit Claude Haiku and got a
response. Confirmed the pipeline worked. Same session: started the Municipal Meeting Scanner.

Built the Business Prompt Library: six production Claude skills: `pch-advisory` (CFO/COO
advisory ops), `regpartner` (SEC private fund compliance), `invcogaap` (ASC 946 accounting),
`sbgc-email` (community email drafting), `website-copy`, and `resume-builder`.

Key lesson: a well-structured system prompt with hard rules and context files is 10x more
useful than a generic prompt. Architecture matters here exactly like it does in code.

---

### Month 2: Master the API (March–April 2026)

**Municipal Meeting Scanner (Mar 9–11)**
Node.js + Playwright visiting ~20 local government websites, pulling agendas and minutes,
sending content to Claude Haiku, and returning housing/zoning items with relevance scores
into a formatted HTML report. First production tool. First lesson in web scraping:
government websites are messy, inconsistent, and slow.

**Workforce Housing Analyzer (Mar → ongoing)**
Leelanau County parcel workbook, now at v102. Each version adds AI-assisted analysis
layers: ownership clustering, parcel size filtering, proximity scoring. First real
experience with Claude as an iterative analytical partner on a live dataset. Also used
Python to extract tax parcel data across Leelanau County, Michigan in minutes versus
$2,500 from the County.

**Kalshi Trading (Apr 2)**
Started as an academic research paper, became a live trading bot on Kalshi (the regulated
prediction market platform). The model is trained to find a signal edge on Bitcoin contracts
and short-dated options. Currently in ML training.

**Obsidian Second Brain (Apr 13 → ongoing)**
Started as Obsidian + Web Clipper for capturing research, articles, and notes, with a
Sunday writing practice. Has since matured into a working synthesis engine: standardized
capture templates, including a new YouTube transcript template, feed Claude-assisted
synthesis on two fronts: synthesized writing and densely linked maps of content.

**Aether Advisors + Monthly Financials Builder (Apr 23)**
Two projects launched the same day. Aether Advisors: building the AI infrastructure for
my wife's marketing company: image generation, marketing program design, brand strategy.
Monthly Financials Builder: Python CLI that takes raw QBO exports and assembles a complete
board financial package with one command. Now used every month for a nonprofit I am Treasurer for.

Key lesson: not every automation needs AI. This one is mostly deterministic, and that's
the right call.

**Email Eval Framework (Apr 2026)**
HTML scoring system for reviewing AI-drafted community emails against non-profit's strict brand
voice and terminology rules. First structured evaluation layer.

**Tax Prep with Claude (April 2026)**
First high-stakes Claude use: worked through a full personal tax filing using Free Tax USA
with Claude as a co-pilot — deduction lookups, edge cases, logic-checking my own reasoning
under real deadline pressure. Not a "project" in the traditional sense, but the experience
that showed me Claude could handle real professional work with the right guidance, not just
demos. Everything else in this portfolio traces back to it.

---

### Month 3: Tools & Agents (May 2026, current)

**Parish Bookkeeping System (Apr 2026)**
Stepped in as interim bookkeeper for a parish (2 churches, a school, and several
ministries). The previous bookkeeper had 30 years of undocumented institutional knowledge.
Now: documenting every process from scratch, integrating platforms with QuickBooks, moving
paper workflows to digital, writing a proper training manual. Claude handles drafting,
summarizing, and process design.

**Resume Builder Skill (May 2)**
After enough manual resume tailoring sessions, formalized it into a Claude skill. Feed it
a job description, it produces a tailored version of my formatted master resume with
pre-approved language pulled from past versions. Trained iteratively over many uses.

**Fraud Finder (May 2)**
Public-data scraper and relationship-mapping agent: pulling Illinois state contract data,
entity registrations, and political contribution records, then using Claude to find
suspicious connections between newly formed LLCs, contractors, and politicians. First
serious agentic pipeline: search, parse, correlate, flag.

**Claude Audit (May 7)**
Python script to audit and clean up a computer's file system using AI: scans, categorizes,
and surfaces what to keep, archive, or delete.

**Family Flow App (started Mar, bulk of work May 2026): ahead of roadmap**
Concept started in March, shipped the real features in late April/early May:
- Shared calendar aggregation for the whole family
- Grocery store integration: reverse-engineered hidden APIs using Claude Code to pull
  weekly deals and inventory (no documentation; inferred structure from network requests)
- Financial dashboard for household spending
- Plaid integration in progress (connecting spouse's accounts)
- Cash flow predictor on Supabase: model logic in progress

The grocery API work was the hardest piece. Claude Code had to infer endpoint structure
from browser network traffic and iterate until the wrappers held. Different level of work.
Will add additional features based on user feedback (my wife).

**Wacker Advisors OS (Mar 2026 → ongoing): ahead of roadmap**
Full operating system for a one-man outsourced CFO/CCO/COO firm. Every workflow automated
or AI-assisted: onboarding, compliance calendars, deliverable tracking, invoice generation,
engagement letters, quarterly reports. Infrastructure is production-ready.

**Kalshi Trading: The Edge Didn't Hold (May)**
The model finished ML training and moved into live paper simulation: 55 settled trades
over a week against a $1,000 bankroll. The verdict was decisive: a calibration study
across 1,274 settled markets, independently confirmed by the live cohort, showed Kalshi's
BTC daily binary markets are already well-calibrated (Brier 0.0032, skill score 0.98). A
directional strategy has no detectable edge. That negative result is the real finding.
The project is now back where it started, as a research write-up.

**007 Trading Agent (May 16 → ongoing): ahead of roadmap**
A multi-agent equities trading system: a from-scratch clone of the published
"TradingAgents" framework. Roughly ten specialized agents ingest market data, argue
opposite sides of every trade, size the position, and clear it against an independent
risk veto. Roughly twenty hardening sprints in: walk-forward backtesting on the deflated
Sharpe, an ablation harness and pandas baselines, and real Alpaca paper-trading
integration. Next up is a multi-day live paper-trading week starting May 26. The track
record becomes the project's research paper.

**Grok Brain Export (May 2026)**
Exporting and cleaning Grok AI conversation history since 2025 and outputs for structured integration
into the Obsidian second brain. Turning raw AI interaction history into searchable,
linked knowledge.

**Working Capital Agent (May 22): ahead of roadmap**
A portfolio-company value-creation demo: an agentic accounts-receivable diagnostic and
collections tool for private-equity portfolios. Deterministic analysis finds where cash is
trapped; Claude writes the board-ready narrative and drafts a tone-matched collection
email for every past-due account; a human approval queue gates every send; a treasury
rollup turns one company's win into a fund-level EBITDA and MOIC lift. All synthetic data,
production-grade logic. Public on GitHub.

**Freight Carrier Optimization Agent (May 22): ahead of roadmap**
The sibling demo, applied to freight. Point it at a manufacturer's twelve-month shipment
history; it re-prices every shipment against live carrier rates (EasyPost, Warp Freight),
decomposes the savings lever by lever, and builds a board-ready EBITDA bridge, then runs
the same play across a whole fund. Deterministic math, one narrow LLM step for the
negotiation scorecard, a Streamlit app and a Jupyter walkthrough off a single codebase.
Public on GitHub.

**Inventory Intelligence Agent (May 2026): ahead of roadmap**
Third in the portfolio value-creation suite. Point it at a distributor's inventory
snapshot and 24 months of demand; it segments the catalog ABC × XYZ, sizes
variability-driven safety stock and EOQ cycle stock, surfaces the dead SKUs and the long
tail trapping working capital, and rolls a single-portco diagnostic up to a fund-wide
pooling play using the classical √N bound. Cross-agent guardrails so it doesn't
double-count what the Freight, Procurement, and Working Capital agents already own.
Public on GitHub.

**Procurement Spend Intelligence Agent (May 2026): ahead of roadmap**
Fourth in the suite, and the one where fund-level leverage matters most. Cleans the
vendor master with rapidfuzz, classifies spend into a 10-category taxonomy, surfaces tail
and maverick spend at the portco level, then builds a unified fund-wide spend cube and
prices cross-portco vendor consolidation against tier-break benchmarks. Output is a
category-by-category negotiation playbook an operating partner can take into a kickoff
meeting the next day. Public on GitHub.

**Twitter Stock Research Pipeline (May 17 → ongoing)**
Turned my X bookmarks into a research system with zero capture-time effort. A scheduled
agent scrapes bookmarks every three days, classifies stock ideas into a dedicated Obsidian
track (flagging what it can't call instead of guessing), and feeds a 500+-ticker tracker
refreshed every weekday morning within an API budget. Interactive Claude sessions do the
judgment work: leaderboard ranking, thesis checks, valuation passes. Key lesson: hidden
constraints (X's DOM virtualization, FMP's real free-tier limits) only surface in
production, never in testing.

**Taste Interview: Voice Profile (May 28, completed June 7, 2026)**
A 100-question interview, conducted by Claude, extracting my personal writing voice into
a reusable profile, based on Ruben Hassid's "I am just a text file," heavily customized:
checkpoint saves every 10 questions, HARD RULE / TENDENCY / PREFERENCE tagging,
draft-on-demand exercises. The interview catches you lying to yourself: under questioning
I reverted to clichés that are on my own banned list, exactly what the profile exists to
pin down. Output: `Voice_Profile_Peter_Hanselmann.md` in the Obsidian vault.

---

### Month 4: Real Products
*Roadmap phase. Agent work started early (see Month 3 above).*

**Forge: AI-Native Fund Accounting ERP (Jun 3 → ongoing)**
The most ambitious build yet: a from-scratch fund administration platform (the category
owned by Allvue, Dynamo, and eFront) with an audit-grade, replayable accounting core and
natural language as the eventual interface. Built with a two-tier Claude workflow: Cowork
sessions as architect/program manager (grounded by my InvCoGAAP skill) producing
versioned phase prompts; Claude Code implementing through explicit gates with hard stop
conditions; adversarial multi-agent review verifying every claim against the code. Eleven
phases largely executed in roughly two days, 150+ tests passing under strict
type-checking. Every hard problem so far has been an accounting judgment or a
process-design question, not a coding question. Code private; this one might be a
product.

**Kalshi Trading: Published (Jun 6)**
The negative result became a paper: *"Are Bitcoin Daily Binary Prediction Markets
Efficient? Calibration Evidence from 1,274 Settled Kalshi Contracts and a Live
Out-of-Sample Trading Experiment"*, now on
[SSRN](https://ssrn.com/abstract=6891438). The project that started April 2 as an
academic question, became a live trading bot, and found no edge, closes as a published
research finding. Project 06 marked ✅ Done.

**Content Factory: a gated short-form content engine (Jun 7 → ongoing)**
The gated-loop pattern pointed at media instead of code. A six-agent system — Trend Scout,
Format Architect, Production Line, Evaluator, and an orchestrator — produces a small
portfolio of faceless niche video accounts, with a scorecard locked before any data exists
and a weekly kill cycle whose Distribution-Reality and Unit-Economics lenses have binding
keep/kill power. A red-team review caught the portfolio being selected on signals unlinked to
revenue, which is exactly what the evaluator gates exist to stop. Foundation stage: scaffold
and Python pipeline built (edge-tts, stock-footage fetch, assembly), nothing live yet.

**Status sweep (Jun 23)**
- **Forge (26)**: the demo I targeted for June 8 landed, and the build kept going. Since
  then: a distribution-waterfall engine, statement renderers, and ASC 946 financial
  statements (Statement of Assets & Liabilities, Operations, Schedule of Investments,
  Financial Highlights) generated from the FactSet, plus `verify-reproducibility` proving
  each fund's signed log replays byte-for-byte against its attestation. ~140 tests green.
  Next up is the valuation-judgment wedge. Full write-up on the project page.

**Status sweep (Jun 25)**
- **Forge (26)**: core is published and at rest — `main` equals `origin/main`, CI green,
  and all five fund anchors replay byte-identical. Recent sessions closed backlog cleanly
  rather than opening new ground: LP self-service (own class economics + a quarterly LP
  report), a real web-build gate in CI, toolchain bumps, and a Next.js security patch.
  Next, deferred to its own checkpointed session, is byte-exact seed surgery to fold a
  fund's reapply step into the seed. Strategic frame now explicit: Forge is the
  reproducible layer-1 of a three-layer "company brain," sold to GPs through Wacker, with
  pricing tied to provable correctness.
- **Twitter Stock Research (24)**: added more tickers and began measuring returns by
  sector — watch-list sectors against everything else — to see where the bookmarked crowd
  clusters versus where performance actually is. Expanding the analysis next.
- **SBGC CLT — STORM (27, new)**: tested STORM and Co-STORM over a built corpus to review
  a community group's community-land-trust research. First run underdelivered — I anchored
  the synthesis on a single referenced doc, which narrowed and biased the output away from
  what the multi-perspective method is for. Logged as a useful negative result; rebuild is
  to feed a broader, balanced corpus and re-run both passes.

**Sass Factory: a gated software factory (Jun 25 → ongoing)**
The Arc's next rung, built. A control plane spawns sandboxed coding agents at a repo and
streams their work live; the "reap" gates every change at the merge boundary — deterministic
`check-all` (ruff, mypy strict, a coverage ratchet, duplicate-code) as gate 1, and an
adversarial review agent that reads the diff and votes merge/block as gate 2 — then proposes
a PR rather than self-merging. It fuses Warren's live observability (Jaymin West's
open-source control plane, credited) with Forge's review-governs-the-plan discipline, built
clean-room. Within days it was self-advancing: a backlog driver runs each deliverable through
a headless agent, gates it, commits on green, and moves to the next — and it is now dogfooding
by building its own backlog through its own control plane. This is the realized version of
the Arc's old aspirational "next move."

**Status sweep (Jun 27)**
- **Sass Factory (28, new)**: the reusable, self-advancing software factory above is built
  and dogfooding — and it pushes The Arc to a 7th rung (a factory that builds, reviews,
  tests, and ships software end to end, currently building itself).
- **Forge (26)**: the deferred byte-exact seed surgery shipped (Jun 26) — a clean `make demo`
  now natively emits a fund's canonical 141-event log with **zero event bytes changed**, and
  the dead reapply path is retired. The one-way door went through without breaking
  byte-identity. Now in progress: attesting per-class LP economics, which meant re-baselining
  the seed and re-pinning anchors; suite is ~580 tests, adversarial skeptic 7/7 green, paused
  at a checkpoint awaiting my merge go. A reseed checkpoint hit a hard stop on a misread the
  skeptic caught — the gate working as designed.
- **Wacker Advisors OS (16)**: now running on live consultancy work rather than waiting in
  the wings; website launch impending.
- **Twitter Stock Research (24)**: watch list keeps growing as bookmarks accumulate;
  expanding the sector-return analysis on the larger set is next.

### Month 5: Advanced Architecture
*Roadmap phase. Work started early (see Month 3 above).*

### Month 6: Reputation & Income
*Not started*

---

*Started: March 1, 2026 · Updated: June 28, 2026*
                                                                                                                                                                                                                                                                                         
