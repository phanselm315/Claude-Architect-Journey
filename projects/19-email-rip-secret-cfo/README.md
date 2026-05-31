# Email Rip — Secret CFO

**Status:** 🔄 Active  
**Started:** May 2026  

## What This Is

Email content scraper and Claude analysis pipeline targeting the Secret CFO newsletter
archive. Pulls, cleans, and categorizes the full archive, then runs Claude over it to
extract frameworks, patterns, and synthesized reference material.

## Architecture

- **Source:** Secret CFO newsletter archive (email)
- **Pipeline:**
  1. Rip — extract email content from archive
  2. Clean — strip headers, footers, formatting artifacts
  3. Categorize — tag by topic (financial strategy, ops, leadership, etc.)
  4. Analyze — Claude extracts frameworks, recurring themes, and actionable patterns
  5. Synthesize — structured reference docs compiled from analysis
- **Output:** Categorized, synthesized reference library from the full archive

## Key Decisions

**Archive-first, then analyze.** Processing emails one at a time as they arrive misses
cross-issue patterns. Building the full archive first means the analysis can surface
themes and frameworks that only become visible across many issues.

**Claude for synthesis, not just summary.** Summarizing each email is easy and mostly
useless. The value is in synthesis: what frameworks appear repeatedly? What principles
show up across different topics? That requires reasoning over the full corpus, not
per-document summarization.

**Structured output over notes.** The goal is a reference library you'd use,
not a collection of AI-generated summaries. Output is organized into topic categories
with cross-references — designed for retrieval, not archiving.

## Lessons Learned

High-quality newsletters are an underused corpus for building domain knowledge. The
Secret CFO archive represents years of CFO-level thinking. Running a synthesis pipeline
over it is faster and more thorough than reading every issue manually — and produces
a structured reference that the original issues don't.

Pipeline design matters more than prompt quality here. The quality of the output is
determined by how well the data is cleaned and structured before Claude ever sees it.

---

*Part of the [Claude Architect Journey](../../README.md)*
