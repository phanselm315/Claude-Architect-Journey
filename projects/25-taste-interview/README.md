# Taste Interview — Voice Profile

**Status:** 🔄 Active (mid-interview)  
**Started:** May 28, 2026  

## What This Is

A structured 100-question interview, conducted by Claude, to extract how I actually think
and write — so any future AI writing task can sound like me instead of like a language
model. Based on Ruben Hassid's "I am just a text file" concept, heavily customized. The
deliverable is a voice profile document that gets prepended to any "write as Peter" task:
LinkedIn posts, cover letters, interview answers, peer DMs. This is my *personal*
register, deliberately separate from the Wacker Advisors brand voice guide — I'm at a
career inflection point, and the profile has to serve whichever path wins.

## Architecture

Seven sections, 100 substantive questions: beliefs and contrarian takes, writing
mechanics, aesthetic crimes, voice and personality, structural preferences, hard nos, and
red flags. The mechanics that make it work:

- **Checkpoint saves every 10 questions** to a WIP file in the Obsidian vault — a context
  overflow at question 87 can't nuke 86 answers.
- **Follow-ups don't count toward the 100.** Otherwise you get 60 real questions and 40
  reframes.
- **Live tagging** of every captured tendency as HARD RULE / STRONG TENDENCY / LIGHT
  PREFERENCE, pulled through at final compilation.
- **Draft-on-demand questions** — "don't describe your style, draft the post" — plus real
  writing samples pasted in so the interviewer can spot patterns I can't self-report.
- Answers dictated by voice where possible, for authenticity.

## Key Decisions

**Personal register first, brand voice deferred.** The original prompt anchored on Wacker
Advisors. I rewrote the grounding around my full career instead, so the profile works for
both the build-the-firm path and the in-house path. A second pass for the firm voice can
come later.

**Customize before running.** Eight modifications to the generic prompt before question
one — checkpointing, tagging, follow-up rules, tone calibration ("senior peer, not
prosecutor"). The prompt engineering was half the project.

## Lessons Learned

The interview catches you lying to yourself. Under questioning I reverted to
"results-driven CPA" clichés — phrasing that's on my own banned list. A self-described
style guide would have enshrined those; an interview with drafting exercises and real
samples exposed them. By question 30 it had pinned over ten hard rules I would never have
articulated unprompted, several confirmed across multiple writing samples.

After a pause around question 38, the interview resumed and now sits around question 80
of 100 (June 5). The checkpoint design did exactly what it was built for — picking back
up cost nothing. Final compilation of the profile is the remaining work.

---

*Part of the [Claude Architect Journey](../../README.md)*
