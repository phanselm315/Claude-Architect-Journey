# Email Eval Framework

**Status:** ✅ Done  
**Started:** Apr 2026  

## What This Is

HTML evaluation system for scoring AI-drafted community emails against strict brand voice
and terminology rules. Built for a nonprofit with detailed style guidelines. First
structured eval layer in the project portfolio.

## Architecture

- **Format:** Single HTML file — self-contained, no server required
- **Input:** AI-drafted email text (paste or upload)
- **Scoring logic:** Rule-based checks against brand voice criteria
  - Prohibited terms and phrases
  - Required structural elements
  - Tone indicators
  - Terminology consistency
- **Output:** Scored report with per-rule pass/fail and overall grade

## Key Decisions

**HTML over a Python script.** The person reviewing emails is not running Python scripts.
HTML opens in a browser, works on any machine, and requires nothing to install. The
output format has to match the operator's workflow, not the builder's preference.

**Rule-based scoring over AI scoring.** Brand voice rules are explicit and enumerable
for this organization. An AI scoring layer would add latency and potential inconsistency
for a task that doesn't require reasoning — just pattern matching. Hard-coded rules are
faster, more transparent, and easier to audit.

**Eval-first thinking.** Building the evaluation framework before scaling email output
volume was the right order. You can't improve what you can't measure. This tool made
it possible to identify which AI-drafting patterns consistently fail the brand test
before those emails went anywhere near a recipient.

## Lessons Learned

Evaluation frameworks are underbuilt in most AI workflows. People spend time on the
generation side and almost none on the measurement side. The result is inconsistent
output that slowly erodes trust in the AI layer.

Explicit rules force clarity about what the brand voice *is*. The process
of building the scoring rubric surfaced several cases where the style guidelines were
ambiguous or contradictory — and those got resolved before they became recurring problems.

---

*Part of the [Claude Architect Journey](../../README.md)*
