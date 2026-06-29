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

| Month | Focus                                                                       | Milestone                                                        |
|-------|-----------------------------------------------------------------------------|------------------------------------------------------------------|
| 1     | **Foundation**: prompt engineering, first API calls, daily tools            | First working API script + system prompt library                 |
| 2     | **Master the API**: CLI tools, PDF automation, eval frameworks              | 3 production CLI tools in active use                             |
| 3     | **Tools & Agents**: web scraping, external APIs, data pipelines             | Scraper-agent + parish bookkeeping system + fraud finder         |
| 4     | **Real Products** *(current — June 2026)*: apps used by real people in real life                    | Family Flow App + Wacker Advisors OS + four-agent PE value-creation suite + Forge fund-accounting ERP |
| 5     | **Advanced Architecture**: multi-agent, ML training, trading systems        | 007 agent live paper run · Kalshi calibration study               |
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
| [PortCo Value-Creation Agent Suite](#portco-value-creation-agents) | Four PE portfolio-company agents — working capital, freight, inventory, procurement. Each pairs a deterministic diagnostic with an LLM judgment layer behind a human approval queue, rolling a single-portco win up to a fund-level EBITDA / MOIC story. |
| [Wacker Advisors OS](./projects/16-wacker-advisors-os/) | The operating system for an AI-native fractional CFO + CCO practice: compliance calendars, deliverable tracking, and document automation. Now running on live consultancy work. |
| [007 Trading Agent](./projects/17-007-trading-agent/) | Multi-agent equities system: ~10 agents ingest data, debate each trade, and clear it against an independent risk veto. Built to produce a live paper-trading research record. |
| [Kalshi Calibration Study](./projects/06-kalshi-trading/) | Academic question → live trading bot → published SSRN finding: BTC daily binaries are well-calibrated with no directional edge. An honest negative result, treated as the product. |
| [Business Prompt Library](./projects/04-business-prompt-library/) | Production Claude skills for CFO/CCO advisory, SEC private-fund compliance, and ASC 946 investment-company accounting. |
| [Monthly Financials Builder](./projects/09-monthly-financials-builder/) | Python CLI that assembles the full monthly board financial package — cover page, donations, expenses, bank statements — from raw QuickBooks Online exports in one command. In monthly use for a nonprofit board. |
| [Parish Bookkeeping System](./projects/11-parish-bookkeeping-system/) | Documented 30 years of undocumented month-end process and automated QuickBooks Online workflows across multiple entities — two churches, a school, and ministries. |

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
| 06 | [Kalshi Trading](./projects/06-kalshi-trading/)                         | 2–3   | Academic paper → trading bot → research finding: live paper-trading and a 1,274-market calibration study showed Kalshi's BTC binaries are well-calibrated with no directional edge. Result published on SSRN (June 2026) | Apr 2, 2026  |
| 07 | [Obsidian Second Brain](./projects/07-obsidian-second-brain/)           | 2–3   | Knowledge system on Obsidian, now a working synthesis engine: standardized capture templates (Web Clipper, YouTube transcripts, X/Twitter bookmark ingest) feed Claude-assisted synthesized writing and densely linked maps of content | Apr 13, 2026 |
| 08 | [Aether Advisors](./projects/08-aether-advisors/)                       | 2–3   | AI-powered marketing company build: AI image generation, marketing program design, brand strategy, SEO/GEO audits               | Apr 23, 2026 |
| 09 | [Monthly Financials Builder](./projects/09-monthly-financials-builder/) | 2–3   | Python CLI: auto-assembles board financial package (cover page, donations PDF, expenses, bank statements) from QBO exports      | Apr 23, 2026 |
| 10 | [Email Eval Framework](./projects/10-email-eval-framework/)             | 3     | HTML evaluation system for scoring AI-drafted community emails against strict brand voice rules                                 | Apr 2026     |
| 11 | [Parish Bookkeeping System](./projects/11-parish-bookkeeping-system/)   | 3     | Documenting 30-year undocumented processes, automating QBO workflows for 2 churches + school + ministries, training new hire   | Apr 2026     |
| 12 | [Resume Builder Skill](./projects/12-resume-builder-skill/)             | 3     | Claude skill that ingests any job description and produces a tailored version of a formatted master resume with approved language | May 2, 2026  |
| 13 | [Fraud Finder](./projects/13-fraud-finder/)                             | 3     | Public-data scraper + agent mapping links between Illinois politicians, newly formed LLCs, and state contract awards            | May 2, 2026  |
| 14 | [Claude Audit](./projects/14-claude-audit/)                             | 3     | Python script to audit and clean up a computer's file system using AI                                                          | May 7, 2026  |
| 15 | [Family Flow App](./projects/15-family-flow-app/)                       | 3     | Personal app: shared calendar aggregation, grocery store hidden API integration (via Claude Code), financial dashboard, Plaid   | Mar 2026     |
| 16 | [Wacker Advisors OS](./projects/16-wacker-advisors-os/)                 | 3     | Full AI-powered operating system for a one-man outsourced CFO/CCO/COO firm. Every workflow automated or AI-assisted            | Mar 2026     |
| 17 | [007 Trading Agent](./projects/17-007-trading-agent/)                   | 3–5   | Multi-agent equities trading system: a from-scratch clone of the "TradingAgents" framework (Xiao, Sun, Luo & Wang, arXiv:2412.20138). ~10 agents ingest data, debate the call, and clear it against an independent risk veto; ~20 hardening sprints in, live paper run begins May 26 | May 16, 2026 |
| 18 | [Grok Brain Export](./projects/18-grok-brain-export/)                   | 3     | Export and clean Grok AI outputs and conversation history for structured integration into Obsidian second brain                 | May 2026     |
| 24 | [Twitter Stock Research Pipeline](./projects/24-twitter-stock-research/)  | 3–4   | Zero-touch pipeline from X bookmarks to a stock-research system: scheduled scrape + AI classification into Obsidian, a 500+-ticker tracker with weekday price refresh (FMP), and on-demand Claude valuation sessions. Now layering trend analysis (crowd vs. street) | May 17, 2026 |
| 25 | [Taste Interview: Voice Profile](./projects/25-taste-interview/)          | 3–4   | 100-question Claude-conducted interview extracting my personal writing voice into a profile any AI writing task can load. Checkpointed, hard-rule tagged, drafting exercises included | May 28, 2026 |
| 26 | [Forge: AI-Native Fund Accounting ERP](./projects/26-forge-fund-erp/)     | 4–5   | From-scratch AI-native fund administration platform: audit-grade, replayable accounting core built via a two-tier Claude workflow (architect sessions → gated Claude Code phases → adversarial multi-agent review) | Jun 3, 2026  |
| 27 | [SBGC CLT — STORM Research Synthesis](./projects/27-sbgc-clt-storm/)       | 3–4   | Test of Stanford's STORM / Co-STORM multi-perspective article generation over a built corpus, used to review a community group's community-land-trust research. First run underdelivered — anchoring on one source doc narrowed the synthesis; rebuild planned | Jun 2026     |
| 28 | [Sass Factory](./projects/28-sass-factory/)                              | 5     | Gated software factory: spawns sandboxed coding agents at a repo, streams their work live, and gates every change at the merge boundary (deterministic `check-all` + an adversarial review agent that votes merge/block) so nothing ships unchecked. Self-advancing — it now builds its own backlog. The Arc's "loops of loops" generalized into a reusable system | Jun 25, 2026 |
| 29 | [Content Factory](./projects/29-content-factory/)                        | 4     | Faceless short-form video engine: a six-agent system (Trend Scout → Format Architect → Production Line → Evaluator) producing a small portfolio of niche accounts, governed by a scorecard locked before any data exists and a weekly kill cycle with binding keep/kill gates. Affiliate-first. Early stage — scaffold built, nothing live yet | Jun 7, 2026  |

### PortCo Value Creation Agents

Four agents shipped as one body of work (May 2026): a private-equity portfolio-company
value-creation suite. Each runs a deterministic diagnostic on one operational lever, uses
Claude for the judgment layer, and rolls a single-portco win up to a fund-level EBITDA and
MOIC story. All public on GitHub, all on synthetic data with production-grade logic.

| #  | Project                         | Month | Description                                                                                                                    | Started      |
|----|---------------------------------|-------|--------------------------------------------------------------------------------------------------------------------------------|--------------|
| 20 | [Working Capital Agent](./projects/20-working-capital-agent/)           | 3–4   | Agentic accounts-receivable diagnostic + collections tool for PE portfolios: deterministic trapped-cash analysis, customer segmentation, Claude-drafted collection emails behind a human approval queue, and a fund-level treasury rollup | May 22, 2026 |
| 21 | [Freight Carrier Optimization Agent](./projects/21-freight-carrier-optimization-agent/) | 3–4 | Agent that re-prices a manufacturer's shipment history against live carrier rates, decomposes freight savings lever by lever, and rolls a single-portco EBITDA bridge up to a fund-level value-creation play | May 22, 2026 |
| 22 | [Inventory Intelligence Agent](./projects/22-inventory-intelligence-agent/) | 3–4 | Agent that segments a distributor's catalog by ABC × XYZ, sizes variability-driven safety stock and EOQ cycle stock, surfaces dead SKUs and the long tail, and rolls a single-portco working-capital release up to a fund-wide √N pooling play | May 2026     |
| 23 | [Procurement Spend Intelligence Agent](./projects/23-procurement-spend-intelligence-agent/) | 3–4 | Agent that cleans the vendor master, classifies spend by category, surfaces tail / maverick / concentration risk, and rolls per-portco procurement savings up to a fund-wide negotiation playbook | May 2026     |

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
- Built the Business Prompt Library: six production Claude skills (CFO/COO advisory, SEC compliance, ASC 946 accounting, community email, website copy, resume). Lesson: a structured system prompt with hard rules beats a generic one tenfold.

**Month 2 — Master the API (March–April 2026)**
- Municipal Meeting Scanner: Playwright pulls ~20 government sites into a scored housing/zoning report.
- Workforce Housing Analyzer: iterative AI parcel analysis (v102+); extracted county tax-parcel data in minutes versus a $2,500 quote.
- Kalshi Trading begins as an academic question and becomes a live BTC paper-trading bot.
- Obsidian Second Brain matures from capture into a Claude-assisted synthesis engine.
- Monthly Financials Builder (QuickBooks board package) and Aether Advisors (marketing-AI infrastructure) launch the same day.
- Email Eval Framework: first structured brand-voice scoring layer.
- Tax Prep with Claude: first high-stakes use — a full personal filing — the experience everything else traces back to.

**Month 3 — Tools & Agents (May 2026)**
- Parish Bookkeeping: stepped in as interim bookkeeper; documented 30 years of undocumented process and automated QuickBooks workflows across multiple entities.
- Fraud Finder: first agentic pipeline — scrape, parse, correlate, flag across public political and contract data.
- Resume Builder skill and Claude Audit (AI-assisted file-system cleanup).
- Family Flow App: shared family calendar, grocery APIs reverse-engineered via Claude Code, Plaid spending dashboard.
- Wacker Advisors OS: the full operating system for a one-person CFO/CCO practice.
- Kalshi: the edge didn't hold — a 1,274-market calibration study found no directional edge. The negative result is the finding.
- 007 Trading Agent: a from-scratch multi-agent equities system, ~20 hardening sprints into a live paper run.
- PortCo Value-Creation suite — working capital, freight, inventory, procurement — shipped as one body of work.
- Twitter Stock Research pipeline, Grok Brain Export, and the Taste Interview voice profile.

**Month 4 — Real Products (June 2026)**
- Forge (AI-native fund-accounting ERP): eleven gated phases in ~two days; an audit-grade, replayable, byte-identical core. Then ASC 946 statements, distribution waterfalls, per-class LP reporting, and byte-exact seed surgery — ~580 tests with adversarial review green.
- Kalshi calibration study published on SSRN.
- Content Factory: a six-agent faceless short-form-video engine with locked eval scorecards and weekly kill-cycle gates.
- Wacker OS moves onto live consultancy work; website launch impending.

**Month 5 — Advanced Architecture (June 2026)**
- Sass Factory: the loops-of-loops generalized into a reusable, self-advancing software factory — gated at the merge boundary, now building its own backlog. The Arc's seventh rung.

**Month 6 — Reputation & Income**
- Underway: this portfolio, outreach, and first paid work.

---

*Started: March 1, 2026 · Updated: June 28, 2026*
