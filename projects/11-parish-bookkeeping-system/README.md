# Parish Bookkeeping System

**Status:** 🔄 Active  
**Started:** Apr 2026  

## What This Is

Interim bookkeeper for a parish — 2 churches, a school, and several ministries. The
previous bookkeeper had 30 years of undocumented institutional knowledge. Scope:
document every process from scratch, integrate all platforms with QuickBooks, move
paper workflows to digital, and write a full training manual for the incoming hire.

## Architecture

- **Accounting platform:** QuickBooks Online
- **Entities:** 2 churches + 1 school + multiple ministry accounts
- **Documentation system:** Process docs written and maintained in structured markdown,
  converted to training manual format
- **AI layer:** Claude for drafting process documentation, summarizing institutional
  knowledge captured in interviews, and designing workflow logic

**Work streams:**
- Process documentation (30 years of tribal knowledge → written SOPs)
- Platform integration (connecting donation platforms, payroll, bank feeds to QBO)
- Paper-to-digital migration (physical records and manual workflows)
- Training manual authoring (designed for a non-accounting hire)

## Key Decisions

**Document before automating.** The instinct was to automate immediately. The right call
was to document first — you can't automate a process you don't fully understand, and
undocumented processes hide exceptions that will break any automation you build on top
of them.

**Claude for documentation drafting, not process design.** The process knowledge came
from interviews and direct observation. Claude's role was converting raw notes and
interview transcripts into clean, readable SOPs — not designing the processes themselves.
That distinction matters for institutional work where accuracy is non-negotiable.

**Training manual targeted at a non-accounting hire.** The incoming person is not a CPA.
The manual had to be written at a level where someone with basic bookkeeping skills could
execute every process without needing to understand the accounting theory behind it.

## Current Milestone

June 2026: the parish hired a full-time bookkeeper. The handoff ran on a quick-summary
package assembled from the Claude-drafted process documentation — the payoff for
documenting first. Remaining work is supporting the transition.

## Lessons Learned

Institutional knowledge is fragile. One departure and 30 years of process logic disappears.
Every organization operating on undocumented knowledge is one resignation away from chaos.
Documentation is infrastructure — it just doesn't look like it until it's missing.

The most important AI use in this project wasn't automation. It was the speed of turning
messy interview notes into clean documentation. What would have taken days of writing
took hours.

---

*Part of the [Claude Architect Journey](../../README.md)*
