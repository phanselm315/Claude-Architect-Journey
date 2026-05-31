# First API Call

**Status:** ✅ Done  
**Started:** Mar 9, 2026  

## What This Is

A six-line Node.js script that made a live call to the Claude API. The foundational proof
of concept that confirmed the pipeline worked.

## Architecture

- **Runtime:** Node.js
- **Model:** Claude Haiku
- **Flow:** Script → Anthropic SDK → Claude API → console output
- Single file. No abstraction layers. Point is just to prove the pipe runs.

## Key Decisions

**Haiku over Sonnet for the first call.** Faster feedback loop, lower cost, and the task
didn't need reasoning depth — just a response. Established the pattern of matching model
to task rather than defaulting to the most capable.

**Node.js over Python.** Familiarity. The goal was to validate the API, not learn a new
runtime at the same time. Python came later once the API behavior was understood.

## Lessons Learned

The first call works in about 10 minutes. The interesting work starts the moment you ask:
*what do I want to build with this?* Every project after this one is the answer
to that question.

---

*Part of the [Claude Architect Journey](../../README.md)*
