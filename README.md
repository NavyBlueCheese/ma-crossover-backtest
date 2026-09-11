# ma-crossover-backtest

A 50/200 day moving-average crossover on SPY, 2010 to 2024, tested against a
buy and hold benchmark using daily prices from Yahoo Finance.

## Method

Long when the 50 day average sits above the 200 day average, flat otherwise.

Signals are shifted forward by one day. The decision is made on a close, so
the position can only be held from the following bar. Without that shift the
backtest trades on information it did not have at the time, which is
look-ahead bias and the most common way a strategy is made to look good on
paper.

Trading costs are charged at 1 basis point on every change in position.

Reported metrics are total return, CAGR, annualised volatility, Sharpe ratio
against a zero risk-free rate, and maximum drawdown.

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
return over this period. That result stands as it is.

Both drawdowns bottom on the same day, 23 March 2020. The COVID decline was
too fast for a 200 day average to react, so the strategy was still fully
invested through it. Trend following protects against slow grinding declines,
not sudden ones.

The strategy is in cash 16.6 percent of the time.

## Running

```
python backtest.py
```

Requires `yfinance`, `pandas`, `numpy` and `matplotlib`. Ticker and window
lengths are constants at the top of the file.
