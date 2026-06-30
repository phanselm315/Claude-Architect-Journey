# Kalshi Trading

**Status:** ✅ Done — paper submitted (June 2026)  
**Started:** Apr 2, 2026  

## What This Is

Started as an academic research project on prediction-market microstructure, became a
live trading bot on Kalshi — the regulated US prediction market — and has now come full
circle back to research. The bot was built to find a directional edge on Kalshi's Bitcoin
daily binary contracts. Both a live paper-trading run and a calibration study across 1,274
settled markets reached the same verdict: the market is already well-calibrated, and a
directional strategy has no detectable edge. That negative result is the finding — now
written up and published.

## The Arc

1. **Research** — prediction-market inefficiency as the starting hypothesis
2. **Signal model** — a lognormal "fair probability" model (Black-Scholes-style spot /
   strike / vol), then a logistic model on structural features
3. **Bot** — data ingestion → fair-prob model → signal vs. market mid-price → order execution
4. **Live paper simulation** — 55 settled paper trades over a week against a $1,000 bankroll
5. **Calibration study** — market mid-price at T-24h scored against realized outcomes
   across 1,274 settled markets
6. **Research write-up** — submitted June 2026 (see Publication below)

## What the Data Showed

Kalshi's BTC daily binary markets are well-calibrated forecasters of their own outcomes.
Scored against realized outcomes, the market mid-price posts a Brier score of 0.0032 and a
skill score of 0.98 over 1,274 settled markets. The 55-trade live paper cohort replicated
it independently — realized win rates matched the market's prices bin for bin. What looked
like edge was the model being wrong, not the market being mispriced: most losing trades
were placed exactly where the market said "this rarely happens," and it rarely did.

## Key Decisions

**Kalshi over crypto exchanges.** A regulated market means reliable data, defined contract
structures, and no custody risk.

**Simulation before live capital.** An edge only counts if it survives honest simulation
against real market data. It didn't — and learning that on paper money is the system
working, not failing.

**Publish the negative result.** A directional model that can't beat a calibrated market
is a real, publishable finding. The discipline is reporting it honestly instead of
overfitting until a backtest looks good.

## Publication

The write-up was submitted in June 2026:

> **"Are Bitcoin Daily Binary Prediction Markets Efficient? Calibration Evidence from
> 1,274 Settled Kalshi Contracts and a Live Out-of-Sample Trading Experiment"**

Full circle: the project that started as an academic research question ends as an
academic paper — with a live trading bot in the middle proving the answer.

## Lessons Learned

A rigorously demonstrated negative result is a result. "The market is calibrated" is more
valuable — and more honest — than a fragile backtested edge that wouldn't survive contact
with real money.

Any model built only on public, stale features — price 24 hours ago, calendar, open
interest — will at best match a market that already prices all of that in, plus the order
flow and fresh information the model never sees. Beating an efficient market needs an
informational edge, not a better curve fit.

Multi-model by necessity. Claude was reluctant to help optimize for trading profit, so I wrote the strategy scripts with Grok instead — and when Grok couldn't write files, I hand-ported its code by copy-paste, the same way a lot of self-taught coders get started from forums and how-to threads. Using the model that fits the task — and being willing to be the integration layer between them — was part of the build.

---

*Part of the [AI Architect Journey](../../README.md)*
