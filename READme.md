# SMA Crossover Backtest — `backtesting.py`

First test run with [`backtesting.py`](https://kernc.github.io/backtesting.py/) using the built-in `GOOG` dataset.  
Implements a basic SMA(100) vs SMA(200) crossover strategy to verify the workflow and get familiar with the API.

---

## Purpose
- Learn `backtesting.py` syntax and structure.
- See how indicators/signals are defined and executed.
- Understand what the generated plot and stats represent.
- Not intended for live trading.

---

## Workflow
1. Load built-in `GOOG` data.
2. Compute SMA(100) and SMA(200).
3. Buy on golden cross (SMA100 > SMA200), sell on death cross (SMA100 < SMA200).
4. Run backtest with:
   - `commission=0.002`
   - `exclusive_orders=True`
5. View stats and plot output.

---

## Output

![SMA Crossover Backtest Output](output/backtest_output.png)

---

## Reading the Plot
- **Top (Equity Curve):** Portfolio value over time, with peak/final return, max drawdown, and drawdown duration.
- **Middle (Price Chart):**  
  - Candles: GOOG price  
  - Blue: SMA(100)  
  - Orange: SMA(200)  
  - Green marker: Buy signal  
  - Red marker: Sell signal  
  - Shaded region = position held
- **Triangles above/below:** Trade-level profit/loss markers.
- **Bottom:** Volume bars.

---

## Key Stats
Returned by `backtest.run()`:
- Return %, CAGR
- Max drawdown % and duration
- Win rate, # trades, best/worst trade
- Sharpe ratio, volatility, exposure %

---

## Notes
- Strategy is lagging and simplistic — only for framework testing.
- Goal is to confirm data → signal → trade → result flow.
- Next steps: try other indicators, add risk controls, test with custom data.

---

## Disclaimer
Educational use only. No claim of profitability.
