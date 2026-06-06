# Twitter Stock Research Pipeline

**Status:** 🔄 Active  
**Started:** May 17, 2026  

## What This Is

A zero-touch pipeline that turns my X (Twitter) bookmarks into a working stock-research
system. I bookmark normally — no sorting, no tagging — and the system does the rest: a
scheduled agent scrapes new bookmarks every three days, classifies anything that names a
ticker or makes an investment case into a dedicated `Stock Research/` track in my Obsidian
vault, and accumulates every mentioned ticker into a master tracker (~500+ tickers,
weighted by how often they're cited). A second scheduled agent refreshes prices and
analyst data every weekday morning. On-demand analysis sessions then pull live quotes,
charts, and news through a Financial Modeling Prep MCP to rank the leaderboard and write
verdicts back into the tracker.

## Architecture

Four moving pieces, three of them fully unattended:

- **Capture** — bookmark on X like a normal person. Zero configuration at capture time;
  classification happens at ingest, by design.
- **Ingest** — the `x-bookmarks-sync` scheduled task scrapes x.com through the browser
  every three days. A classifier routes stock ideas to `Stock Research/`, general ideas to
  the wiki, and flags ambiguous items for review instead of guessing. Privacy is built in:
  my handle is scrubbed before anything touches disk, pure-political content is dropped,
  and a post-run grep verifies the scrub.
- **Track** — every stock note carries `tickers` and `date_seen` frontmatter, which feeds
  `ticker_master.json` and a multi-sheet `Ticker Tracker.xlsx` (price, all-time high,
  sector, analyst consensus, deeper-analysis column). A weekday scheduled task refreshes
  prices via FMP within an API budget, backfilling most-cited tickers first, and writes a
  new dated file every day — never overwriting. A yfinance script on my machine handles
  bulk five-year history and ratings syncs.
- **Research** — interactive Claude sessions for the judgment work: ranking the
  leaderboard, ad-hoc thesis checks, and "what's cheap and has room" valuation passes,
  with verdicts written back into the tracker.
- **Trend analysis (newest layer, June 2026)** — crossing the crowdsourced signal from X
  against bulge-bracket sell-side research (via Schwab) inside the vault's Stock Research
  track: where the crowd and the street agree, disagree, or haven't noticed each other yet.

## Key Decisions

**Classify at ingest, not at capture.** I refused to configure clipper destinations or
sort bookmarks manually. The AI classifies on arrival and flags what it can't call —
correcting a misroute early teaches the pattern.

**Stock Research lives outside the wiki.** Investment ideas have a different lifecycle
than knowledge notes. The weekly wiki ingest never touches the stock track.

**Never overwrite the tracker.** Daily dated versions and backups. Boring, and exactly
why a bad refresh has never cost me data.

**Budget-aware data pulls.** FMP's free tier is narrower than advertised, so the refresh
prioritizes by citation count and backfills the long tail over time instead of failing
loudly on day one.

## Lessons Learned

Hidden constraints surface only in production. X's bookmarks page virtualizes its DOM, so
a single scrape sees only a handful of posts — deep catch-up needs a manual scroll first.
FMP's documented coverage and its actual free-tier allowlist are two different things.
Neither showed up in testing; both showed up in the schedule.

The frontmatter decision paid for itself. Putting `tickers` and `date_seen` on every note
from day one is what made the price tracker possible later without re-touching a single
note.

Builds on the [Obsidian Second Brain](../07-obsidian-second-brain/) (Project 07) — same
vault, same capture discipline, different track.

---

*Part of the [Claude Architect Journey](../../README.md)*
