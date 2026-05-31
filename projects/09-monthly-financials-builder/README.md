# Monthly Financials Builder

**Status:** ✅ Done  
**Started:** Apr 23, 2026  

## What This Is

Python CLI that takes raw QuickBooks Online exports — Excel and PDF — and assembles a
complete board financial package with one command. Generates formatted cover pages,
donation schedules, and expense reports via ReportLab; strips noise pages from bank
statements; merges everything into a single board-ready PDF. In active monthly use for
a nonprofit.

## Architecture

- **Runtime:** Python CLI
- **Input:** Raw QBO exports (Excel workbooks + PDF bank statements)
- **Processing:**
  - `openpyxl` / `pandas` — parse and transform Excel data
  - `ReportLab` — generate formatted cover pages, donation schedules, expense reports
  - `pypdf` — strip bank statement noise pages, merge all components
- **Output:** Single board-ready PDF, consistently formatted every month
- **No AI layer** — deterministic logic throughout (see Key Decisions)

## Key Decisions

**No AI in this pipeline.** The data is structured, the output format is fixed, and the
logic is deterministic. Adding Claude would have added latency, cost, and a potential
failure mode with no corresponding benefit. The right tool for a deterministic problem
is deterministic code.

**ReportLab over a templating approach.** The output needs to match an existing board
package format exactly — fonts, margins, headers, page numbering. ReportLab gives
pixel-level control. Templates would have required ongoing adjustments every time the
format drifted.

**CLI over a UI.** The operator is technical enough to run a command. A UI would have
added weeks of build time for a tool that runs once a month. CLI ships fast and does
the job.

## Lessons Learned

Not every automation needs AI. The instinct when building AI systems is to add AI to
everything. That's wrong. Deterministic problems deserve deterministic code — it's
faster, cheaper, and more reliable.

The most satisfying part of this project: a task that used to take 45 minutes of
copy-paste and reformatting now runs in under 10 seconds. That's the automation doing
exactly what it should.

---

*Part of the [Claude Architect Journey](../../README.md)*
