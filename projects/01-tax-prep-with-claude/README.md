# Tax Prep with Claude

**Status:** ✅ Done  
**Started:** Early 2026  

## What This Is

Used Claude alongside Free Tax USA to work through a full personal tax filing. First
high-stakes, real-world AI use — interpreting edge cases, checking deductions, validating
logic. Not a build in the traditional sense — a tool use. The point was finding out
whether Claude could handle work where the cost of a wrong answer was real money and an
IRS letter.

## Architecture

Not a build — a tool-use pattern. Two pieces:

- **Free Tax USA** for the math, the calculations, and the e-file
- **Claude** for the judgment calls in between — deduction lookups, edge cases, logic
  checks on my reasoning

What this looked like in practice:

- **Deduction lookups** — pulled current IRS limits, phase-outs, and qualifying criteria
  for credits I wasn't sure applied
- **Edge cases** — talked through unusual line items where the right treatment isn't
  obvious from the form instructions
- **Logic-checking** — explained my reasoning back to Claude and asked it to find the
  hole; a second opinion on every judgment call

## Key Decisions

**Claude as co-pilot, not replacement.** I drove every line; Claude advised. Filing
software is the right tool for arithmetic and submission. Claude is the right tool for
the judgment calls in between.

**Free Tax USA over a CPA, this year.** Bringing a CPA into a straightforward personal
return is overkill. With Claude in the loop, "straightforward" stretches further than it
used to — I caught a couple of items I'd have missed on my own. And I'm a CPA.

## Lessons Learned

This is the project that convinced me Claude could do real professional work, not just
demos. Working through a real return — with real numbers, real consequences, and the
deadline pressure of April — is a different test from prompting it to write a poem. It
passed. Everything else in this portfolio traces back to that.

The co-pilot pattern stuck. I use the same shape for legal questions, accounting
research, and any judgment call where I want a second pair of eyes that's faster than a
human and disciplined enough to push back.

---

*Part of the [Claude Architect Journey](../../README.md)*
