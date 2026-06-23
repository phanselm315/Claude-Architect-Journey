# Forge — AI-Native Fund Accounting ERP

**Status:** 🔄 Active — working demo shipped; now through ASC 946 statements  
**Started:** June 3, 2026  
**Code:** Private build — details deliberately high-level here  

## What This Is

The most ambitious build of the journey so far: a from-scratch, AI-native fund
administration and investment-company accounting platform for private funds — the
category owned today by incumbents like Allvue, Dynamo, and eFront. Two bets define it.
First, audit-grade trust: every financial fact lives in an append-only, cryptographically
verifiable record, and every report can be replayed and proven byte-identical from that
record. Second, natural language as the eventual interface for querying and report design
— but only on top of a deterministic accounting core that makes the answers trustworthy.
The deterministic core is what's being built now.

This is where fifteen years of fund-accounting and audit domain knowledge meets everything
the previous 25 projects taught me about building with Claude. I've migrated funds onto
the incumbent platforms; this time I'm building the thing.

## How It's Being Built

The build process is the story I can tell publicly. A two-tier Claude workflow:

- **Cowork as architect and program manager.** Sessions where Claude and I resolve design
  questions in structured decision batches, grounded by my custom InvCoGAAP skill (ASC 946
  investment-company GAAP). Output: dated, versioned phase prompts and amendment files
  with an explicit precedence order.
- **Claude Code as the implementation engine.** Each phase prompt is handed off verbatim
  and implemented autonomously through explicit gates with hard stop conditions —
  "if any task would force X, STOP and report." No vibes-based progress.
- **Adversarial multi-agent review.** Independent reviewer agents — one engineering, one
  fund-admin SME — verify every load-bearing claim directly against the code, and an
  arbiter agent ranks the fix list. This review caught the demo overstating itself in
  several places; the fix principle became a rule: *fix what makes the demo a lie, defer
  what's merely incomplete.*
- **Persistent project memory.** A living lessons-learned file where every gotcha and
  every binding decision gets logged, so no session starts from zero.

Fifteen-plus build phases planned and executed across the run, with
the test suite (~140 passing tests, strict type-checking across the codebase) holding the
line throughout. The first working demo landed on schedule in early June; the build has since pushed past the demo into the accounting engines themselves.

## Current Milestone

The demo is real and running: sign in, then an LP-to-portfolio-company drill-in that
computes indirect ownership exposure deterministically from the event log, plus per-fund
browse. Since that first demo, the build has added the engines that make it an accounting
system rather than a graph:

- **Distribution-waterfall engine** — tiered GP/LP economics computed straight from the log.
- **Statement renderers and ASC 946 financial statements** — Statement of Assets &
  Liabilities, Statement of Operations, Schedule of Investments, and Financial Highlights,
  generated from the FactSet.
- **`verify-reproducibility`** — replays every fund's signed, hash-chained log and proves
  the projection-state hash byte-for-byte against the issued attestation, so tampering or
  drift is detectable after the fact.

Next: the valuation-judgment wedge — making each mark's rationale a signed, permanent part
of the record — and per-LP statement fan-out from the dimensioned allocation lines.

## Key Decisions

**Domain expert in the loop, on the record.** Claude drafts the accounting logic; I
correct it as the CPA — and the corrections get logged, not just applied. The marketplace
scan found no existing Claude skill or tool that does fund accounting at all. That gap is
the opportunity.

**Gates, not momentum.** Big phases get subdivided rather than rushed at the end of a long
context window, and irreversible steps get their own focused, pre-planned sessions.

**Honesty as a feature.** After the adversarial review, demo claims that the code couldn't
back were treated as bugs of the highest severity.

## Lessons Learned

An AI can write production-grade accounting software in days — if a domain expert designs
the decision process around it. Every hard problem so far has been an accounting judgment
or a process-design question, not a coding question. The two-tier prompt-file workflow
(architect sessions producing versioned prompts, implementation gated behind verification)
is the most repeatable engineering pattern I've found in six months of building.

And: adversarial review is non-negotiable. The system was confidently wrong in ways that
only an agent tasked with *proving the demo dishonest* actually caught.

---

*Part of the [Claude Architect Journey](../../README.md)*
