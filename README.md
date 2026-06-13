
FX Statistical Arbitrage — Cointegration Pairs Trading

Finds a cointegrated pair among G10 USD FX rates and trades mean-reversion of
the spread. A research backtest on real data.

Method
- Engle-Granger cointegration test on every pair; trade the most cointegrated.
- Rolling hedge ratio (rolling OLS) and rolling z-score of the spread.
- Enter when |z| > 2 (fade the deviation), exit when |z| < 0.5.
- Signals lagged one day, transaction costs on each position change,
  in-sample / out-of-sample split.

Running it
```bash
pip install yfinance statsmodels pandas numpy matplotlib
```
Run the notebook top to bottom. Saves `fx_statarb_results.png`.

Results
*Paste the cointegration result, performance tables + chart here after running.*

Limitations
- PnL is measured in log-spread units with a time-varying hedge ratio, a
  standard educational simplification rather than an exact tradable return.
- Cointegration found in-sample can break out-of-sample — which is exactly why
  the OOS split matters.
- G10 USD pairs share the USD leg, so apparent cointegration can be partly
  driven by common USD moves.
