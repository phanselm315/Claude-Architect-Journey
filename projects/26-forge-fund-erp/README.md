# Forge — AI-Native Fund Accounting ERP

**Status:** 🔄 Active — core published, byte-identical reproduction; per-class LP economics attestation in progress  
**Started:** June 3, 2026  
**Code:** Private build — details deliberately high-level here  

## What This Is

> **Forge is an AI-native ERP for funds and their portfolio companies that keeps books so clean and reproducible that audit and compliance cost almost takes care of itself.**

Most emerging managers can't easily prove how they got a number — a mark, a capital
balance, a fee calc — until an auditor or LP asks, and then it's a scramble. Forge fixes
that at the source: every economic event, from a capital call down to a portfolio
company's operating expense, is recorded once on a signed, reproducible ledger, and the
books follow by rule. The result is audit-ready books as a deliverable, and a valuation
you can defend without a fire drill.

This is where fifteen years of fund-accounting and audit domain knowledge meets everything
the previous 25 projects taught me about building with Claude. I've migrated funds onto
the incumbent platforms — Allvue, Dynamo, eFront; this time I'm building the thing.

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

**At rest and fully published (June 25).** The core is stable, not mid-build: `main`
equals `origin/main`, CI is green on both jobs, and all five fund anchors replay
byte-identical against their attestations. The last several sessions closed a run of small
backlog items cleanly rather than opening new territory:

- **LP self-service (closed Jun 24)** — an LP can see their own class economics plus a
  quarterly LP report. This is the investor-facing surface Wacker would hand a GP's LPs.
- **CI hygiene, web build gate, and a security patch (Jun 25)** — added a real web-app
  build step to CI (the root cause turned out to be a dev-mode flag leaking into the
  build, not the framework bug the backlog had assumed), bumped the toolchain, and applied
  the Next.js security patch that closes a known CVE chain.

The architecture underneath: an event-sourced ERP where each fund's git repo is the source
of truth, Postgres is a rebuildable projection cache, every event is Ed25519-signed and
hash-chained, and `forge verify-reproducibility` checks the attestations — running locally
via Docker Compose.

**The one-way door went through (Jun 26).** The byte-exact seed surgery I'd deferred —
folding a fund's reapply step into the seed so a clean `make demo` natively emits its
canonical 141-event log — shipped cleanly. The standalone reapply path is retired and
**zero event bytes changed** against the prior live log; published, both CI jobs green,
briefly back at rest. The step treated like a one-way door went through without breaking
byte-identity.

**Now: per-class LP economics, attested (Jun 26–27, in progress).** Extending the
attestation layer so each share class's economics are provable, which meant re-baselining
the seed and re-pinning the registry and fund anchors. The suite is now ~580 tests with
the adversarial "skeptic" reviewers 7/7 green; the work is paused at a checkpoint awaiting
my go to merge. One honest note from the run: a reseed checkpoint hit a hard stop on a
misread — a fund re-pin that looked like a bug turned out to be expected registry coupling,
and the skeptic caught the misread before it became a "fix." The gated stop did exactly
what it's there for.

## Key Decisions

**Domain expert in the loop, on the record.** Claude drafts the accounting logic; I
correct it as the CPA — and the corrections get logged, not just applied. The marketplace
scan found no existing Claude skill or tool that does fund accounting at all. That gap is
the opportunity.

**Gates, not momentum.** Big phases get subdivided rather than rushed at the end of a long
context window, and irreversible steps get their own focused, pre-planned sessions.

**Honesty as a feature.** After the adversarial review, demo claims that the code couldn't
back were treated as bugs of the highest severity.

**The strategic frame.** Forge is the reproducible layer-1 of what I think of as a
three-layer "company brain." The buyer is a GP, reached through Wacker Advisors acting as
an outsourced operational CFO; the thesis is that *reproducible-for-anyone* collapses
audit and compliance cost toward zero, with pricing tied to provable correctness rather
than hours. The end state is real-time continuous reconciliation — 