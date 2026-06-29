# Content Factory — Gated Short-Form Content Engine

**Status:** 🔄 Active — foundation built (scaffold + pipeline), nothing live yet  
**Started:** June 7, 2026  

## What This Is

A faceless short-form video engine: a small portfolio of niche accounts produced by a
six-agent system and governed by a locked evaluation scorecard and a weekly kill cycle. The
thesis isn't "make the best video" — it's that the system's value is *killing losers fast*,
not picking winners up front. Monetization is affiliate-first through a separate niche brand,
deliberately kept apart from my advisory work.

## Architecture

- **Six agents.** An Orchestrator coordinates a Trend Scout (builds opportunity boards and
  selects niches), a Format Architect, a Production Line, and an Evaluator. Each agent is a
  versioned playbook, not a one-off prompt.
- **Python pipeline (`04_Pipeline/`).** Scaffolded production path: text-to-speech (edge-tts),
  stock footage fetch (Pexels / Pixabay), and assembly. Built in Claude Code as its own repo
  inside the project so it gets git and fast iteration.
- **The eval layer is the point.** The scorecard is locked *before any data exists* so losers
  can't be rationalized later. Weekly "Lens Gates" — a Distribution Reality check and a Unit
  Economics check — carry binding keep/kill power; a full six-agent red-team review runs at
  phase gates, not weekly.

## Key Decisions

**Lock the scorecard before the data.** Decide what "good" means while you still have no
results, so you can't move the goalposts once you're attached to an account.

**Gates with teeth, or don't bother.** A red-team review found the portfolio had been selected
for eight weeks on signals that weren't linked to revenue. The fix was to give the weekly
lenses *binding* kill/keep authority — an evaluator that can't kill is just commentary.

**Don't measure what you can't observe.** A metric the platforms don't actually expose
(competitor retention) was quietly driving a huge share of every decision. Anchoring scoring
to things I can truly measure beat a precise-looking number built on uncollectable data.

**Compliance and labor as hard constraints.** A mandatory human creative pass per video
(platform ToS), and a labor cap that makes "net profitable" testable rather than a story I
tell myself.

## Lessons Learned

This is the same pattern as the rest of the portfolio — a gated agent loop where the
*verification* is the product — pointed at media instead of code or accounting. The hardest
part wasn't generating content; it was designing an honest scoreboard that kills my own work
before I get attached to it.

---

*Part of the [AI Architect Journey](../../README.md)*
