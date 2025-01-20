# Gaming-Stocks-Data-analysis-using-ARIMA-family

# Time Series Analysis of Ubisoft Stock Data

## Introduction
This report analyzes Ubisoft stock prices using ARIMA and SARIMAX time series models. The analysis includes:

1. Data Collection
2. Stationarity Testing
3. Model Fitting and Optimization
4. Residual Diagnostics
5. Forecasting

---

## Data Collection
Data was sourced using Yahoo Finance (`yfinance`), retrieving historical prices for Ubisoft (ticker: `UBI.PA`). The time frame was up to January 12, 2025.

---

## Stationarity Testing
### Augmented Dickey-Fuller (ADF) Test:
- Null Hypothesis: Data has a unit root (non-stationary).
- Result: **p-value < 0.05** indicates the series is stationary after differencing.

---

## Model Fitting
### ARIMA Model:
- **Order Selection**: Automated using `auto_arima`.
- Final Order: (p=1, d=1, q=1).

### SARIMAX Model:
- Seasonal component included to address periodic patterns.
- Final Order: SARIMAX(1, 1, 1)(1, 0, 1, 12).

---

## Residual Diagnostics
Residual plots showed:
- White noise distribution.
- Autocorrelation within acceptable bounds.

### Ljung-Box Test:
- Null Hypothesis: Residuals are uncorrelated.
- Result: Passed (p-value > 0.05).

---

## Forecasting
The model produced a forecast for Ubisoft stock prices over a 30-day horizon. Confidence intervals were included to account for uncertainty.

### Visualization:
- Actual vs Predicted values plotted.
- Forecasts extended with shaded confidence regions.

---

## Conclusion
- **Model Performance**: ARIMA and SARIMAX models effectively captured trends and seasonality.
- **Limitations**: Forecast accuracy is sensitive to outliers and external market conditions.
- **Future Work**: Explore hybrid models (e.g., ARIMA + GARCH) for volatility modeling.

---

## References
- Statsmodels documentation
- PMDARIMA for automated ARIMA
- Yahoo Finance API for data collection
