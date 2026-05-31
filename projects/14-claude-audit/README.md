# Claude Audit

**Status:** ✅ Done  
**Started:** May 7, 2026  

## What This Is

Python script that points at a directory tree, walks it, and uses Claude to classify
what's there into keep / archive / delete buckets. Built to do in one pass what years of
"I'll get to that later" never does — surface what's worth keeping and put the rest on a
list I can act on.

## Architecture

- **Runtime:** Python
- **Walk:** `pathlib` traversal across the target tree, collecting filename, extension,
  size, last-modified date, and a small content sample for text files
- **Classify:** Claude categorizes each item by likely purpose and current relevance.
  The prompt asks for a verdict plus a short reason, so every recommendation has a
  justification on the line.
- **Surface:** Output is a categorized list — keep, archive candidates, delete
  candidates — written to a markdown file. Nothing is deleted automatically.

## Key Decisions

**Recommend, don't delete.** A tool that auto-deletes is a tool I won't run twice. The
output is a worksheet the operator (me) acts on. Cost of a mistake is zero; the model
can be wrong on one file in a hundred without breaking anything.

**Sampled content, not full read.** Reading every file's contents is slow and
unnecessary for a categorization pass. A short sample tells Claude enough to call most
documents correctly. The handful of ambiguous cases get flagged for a closer look.

**Python over a desktop tool.** Filesystem cleanup tools exist, but they're rules-based —
they don't know what *this* old proposal draft is. The LLM layer is the whole point.

## Lessons Learned

The classify-then-confirm pattern is the right shape for any agent that touches files:
the model proposes, the human commits. Same discipline as the Working Capital Agent's
human-in-the-loop email queue (Project 20) — the agent does the work, the human keeps
the send / delete button.

A small content sample beats a full file read for most categorization tasks. The pass
runs fast, costs nothing in accuracy on the easy cases, and flags the hard cases for
review.

---

*Part of the [Claude Architect Journey](../../README.md)*
