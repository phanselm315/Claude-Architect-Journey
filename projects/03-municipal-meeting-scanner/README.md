# Municipal Meeting Scanner

**Status:** ✅ Done  
**Started:** Mar 9, 2026  

## What This Is

Node.js + Playwright + Claude API. Scrapes ~20 local government websites weekly, extracts
housing and zoning agenda items with relevance scores, and outputs a formatted HTML report.
First production tool.

## Architecture

- **Runtime:** Node.js
- **Scraping:** Playwright — headless browser to handle inconsistent site structures
- **AI layer:** Claude Haiku scores each agenda item for housing/zoning relevance (0–10)
- **Output:** Formatted HTML report with items grouped by municipality and score
- **Schedule:** Weekly — designed to run unattended

**Flow:**  
Site list → Playwright scrapes each URL → raw text → Claude scores and extracts items →
HTML report generated

## Key Decisions

**Playwright over simple HTTP fetch.** Government websites are often poorly structured,
JavaScript-rendered, or behind rate limiting. Playwright handles all of it. Added
complexity but the alternative was brittle scrapers that broke on the first real site.

**Claude Haiku for scoring.** Relevance scoring doesn't need deep reasoning — it needs
speed and cheap per-call cost across 20 sites. Haiku was the right model. Sonnet would
have been overkill and 5x the cost for the same output.

**HTML output over CSV or JSON.** The consumer of this report is a human doing a weekly
scan. HTML renders immediately, is shareable, and requires no tooling to read. Keep the
output format matched to how it will be used.

## Lessons Learned

Government websites are messy, inconsistent, and slow. Some have no structure at all.
Some block bots. Some have PDFs with no extractable text. The scraper required more
edge-case handling than any other part of the project.

First real lesson in production scraping: **budget 3x the time you think you need for
the data extraction layer.** The AI part is fast. The web part is where projects stall.

---

*Part of the [Claude Architect Journey](../../README.md)*
