# 007 Trading Agent

**Status:** 🔄 Active  
**Started:** May 16, 2026  

## What This Is

A multi-agent equities trading system — a working clone of the published "TradingAgents"
multi-agent framework, rebuilt from scratch on the native Anthropic SDK. Specialized
agents ingest market data, analyze it, argue opposite sides of every trade, size the
position, and clear it against risk limits before anything reaches a broker. Built May 16;
now running a live, multi-day paper-trading week against a real brokerage account — the
track record that becomes the project's research paper.

## Architecture

**Multi-agent** — roughly ten specialized agents, each with a distinct role, passing
structured (Pydantic) messages forward. No agent acts without upstream confirmation:

- **Data + analyst agents** — normalize market data; analyze fundamentals and price/volume
- **Bull and Bear researchers** — argue opposite sides of each candidate; the debate
  between them *is* the signal
- **Trader** — turns the debate into a BUY / SELL / HOLD decision
- **Risk Manager** — an independent veto against position limits and drawdown rules
- **Portfolio Optimizer + Fund Manager** — position sizing, execution, broker submission

**Backtesting** — walk-forward with in-sample / out-of-sample folds, a 5-day embargo,
parameters frozen across every OOS window, an ablation harness, and pure-pandas baselines
(buy & hold, MACD, SMA crossover). Go / no-go runs on the deflated Sharpe ratio, not raw
Sharpe.

**Execution** — real Alpaca paper-trading integration: tick-size rounding, live fill
reconciliation, a dry-run broker for offline replay, price-freshness guards, and a
daily-run automation wrapper.

## Key Decisions

**Multi-agent over a monolithic model.** A single model making every decision is a single
point of failure and a black box. Specialized agents make each component testable,
replaceable, and auditable.

**The Risk Manager is independent.** It can't be a sub-function of the same model
generating trade ideas — the veto has to sit outside the thing it's checking.

**Backtest → simulation → live, in that order.** Each stage only earns the next. The same
discipline as Kalshi Trading (Project 06).

**Honest metrics.** The deflated Sharpe drives decisions; raw Sharpe only sanity-checks
that the engine ran. Guardrails flag short-window and low-trade-count artifacts directly
in the output, so a flattering number can't pass review unchallenged.

## Current Milestone

Roughly twenty hardening sprints in, the infrastructure the whole build was for is done.
The multi-day live paper-trading run against a real Alpaca paper account began May 26,
2026 and is still going as of June 6 — live data and trading testing, extended past the
original five-session plan to build a longer record. That track record — with a
buy-and-hold benchmark and per-decision data-freshness evidence — becomes the results
section of a research paper modeled on the original TradingAgents paper. The system is
HOLD-biased by design; a flat or zero-trade week is recorded honestly as a result, not
patched into a better-looking one.

## Lessons Learned

Multi-agent systems need more upfront design than a single model — but they compound
faster. Once the framework is solid, adding a signal source or improving one agent doesn't
mean rebuilding the system.

Silent failures are the real enemy. Each high-level fix unblocked the pipeline and
immediately surfaced the next bug downstream — the right move is to budget for that next
layer rather than treat the pipeline as "fixed."

A guardrail that lives only in an agent's reasoning is invisible to the next reader.
Promote it into code, and into the artifact itself, so the caveat travels with the result.

The first real broker interaction surfaces breakage no test reached. Verify against the
real adapter, not just an in-house stand-in.

---

*Part of the [Claude Architect Journey](../../README.md)*
