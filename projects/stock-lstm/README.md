# Samsung Electronics Stock Forecasting with LSTM

These notebooks explore one-step-ahead stock-price prediction with an LSTM and a 60-day sliding window.

## Files

- [`StockPrediction.ipynb`](StockPrediction.ipynb): univariate prediction using the closing price.
- [`MultiVariable.ipynb`](MultiVariable.ipynb): an unfinished experiment that attempts to add investor-flow features.

## Current status and limitations

The univariate notebook scales the full downloaded series before creating sequences. For a valid time-series evaluation, split by date first, fit preprocessing on the training period only, and evaluate on a later held-out period. The multivariable notebook contains a saved column mismatch error and a partial fallback cell; it is not a complete runnable experiment.

The notebooks retrieve external market data and require their Python dependencies. Record the data source, retrieval date, date ranges, split, baseline, metrics, and limitations before interpreting results. This is a learning project, not financial advice or a validated forecasting result.
