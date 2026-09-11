# ma crossover backtest

A 50/200 day moving-average crossover on SPY, 2010 to 2024, tested against a
buy and hold benchmark using daily prices from Yahoo Finance.

## Results

```
                  STRATEGY    BUY & HOLD
Total return        291.5%        545.9%
CAGR                10.10%        14.06%
Volatility          14.04%        16.93%
Sharpe ratio          0.76          0.86
Max drawdown        -33.7%        -33.7%
Trades made             13
```

The strategy underperforms buy and hold on both return and risk-adjusted
return over this period.

The COVID decline was too fast for a 200 day average to react so the strategy was still fully
invested through it. Trend following protects against slow grinding declines.

The strategy is in cash 16.6 percent of the time.
