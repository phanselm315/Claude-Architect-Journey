# Fraud Finder

**Status:** 🔄 Active  
**Started:** May 2, 2026  

## What This Is

Public-data scraper and relationship-mapping agent. Pulls Illinois state contract data,
entity registrations, and political contribution records, then uses Claude to surface
suspicious connections between newly formed LLCs, contractors, and politicians. First
serious agentic pipeline in the portfolio.

## Architecture

- **Runtime:** Python
- **Data sources (all public record):**
  - Illinois state contract awards database
  - Illinois Secretary of State entity registrations
  - Illinois political contribution records
- **Agent pipeline:**
  1. Scrape — pull and normalize records across sources
  2. Parse — extract entity names, dates, dollar amounts, principals
  3. Correlate — link entities across datasets (name matching, address overlap, formation dates)
  4. Flag — Claude evaluates connection patterns and scores suspicion level
- **Output:** Flagged relationship maps with supporting data citations

**Agentic pattern:** Search → parse → correlate → flag. Each stage feeds the next.
Claude handles the reasoning layer (what's suspicious vs. coincidental); code
handles data extraction and normalization.

## Key Decisions

**Public data only.** Everything this agent touches is available to any citizen. No
credentials, no scraping behind logins, no gray areas. The point is to demonstrate what
can be found in data that's already public and already paid for by taxpayers.

**Claude for the reasoning layer, code for the data layer.** The pattern-matching and
correlation work is deterministic enough for code. The judgment call — "is this actually
suspicious or just a common name?" — requires reasoning. That's where Claude earns its
place in the pipeline.

**Flag, don't conclude.** The output is flagged connections with supporting data, not
accusations. The system surfaces what's worth a human look; it doesn't make the call.
That's the right design for any investigative tool.

## Lessons Learned

First serious agentic pipeline — the point where "using AI" became "designing an agent
system." The difference is: an AI tool answers a question. An agent pipeline executes
a multi-step process, passing outputs forward as inputs, and handles failures at each
stage independently.

The relationship-mapping logic developed here is a candidate signal layer for the
007 Trading Agent (Project 17) — same pattern-detection architecture, different domain.

Public data is dramatically underused for accountability work. The data exists. The
barrier has always been the time required to cross-reference it. That barrier is gone.

---

*Part of the [Claude Architect Journey](../../README.md)*
