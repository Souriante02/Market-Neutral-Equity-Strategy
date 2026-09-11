# Market-Neutral Equity Strategy

Long momentum equities, hedged with index futures. Backtested 2013–2025, net of costs.


## What it does

Each month the strategy:

1. Ranks US equities by 6–1 month momentum (six-month lookback, skipping the most recent month)
2. Buys the top 10, equal-weighted, capped at three names per sector
3. Estimates the portfolio's beta to SPY over a rolling 252-day window
4. Shorts E-mini S&P 500 futures sized to offset that beta
5. Rebalances, net of stock turnover and futures roll costs

The aim is to isolate stock-selection alpha from broad market direction.

## Results (2013–2025, 147 months)

| Metric | Market-neutral, net of costs |
|---|---|
| Monthly alpha (CAPM regression) | 0.90% |
| t-statistic | 3.54 |
| p-value | < 0.001 |
| Ex-post beta vs SPY | −0.02 |
| Maximum drawdown | −12.4% |

Sharpe, Calmar, monthly win rate, turnover and cost drag are computed in the notebook.
Robustness was checked across momentum lookback windows and portfolio sizes, and exit
rules were defined for drawdown and beta-neutrality failure.

## The conclusion

This is in-sample evidence, not proof of live tradability. Specifically:

- The universe is fixed and chosen with hindsight, so survivorship bias is not controlled for
- Parameters were selected over the same period they were tested on
- Market impact is not modelled
- One market, one regime, one thirteen-year window

A promising course result. Not a strategy.

## Background

Built during the Machine Learning in Finance summer programme run by the University of
Cambridge and Shanghai University of Finance and Economics, July 2026.
