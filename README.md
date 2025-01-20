# Time Series Analysis of Ubisoft and Take-Two Interactive Stock Data

## Introduction
This report analyzes stock prices for Ubisoft (`UBI.PA`) and Take-Two Interactive (`TTWO`) using ARIMA and SARIMAX time series models. The analysis covers:

1. Data Collection
2. Stationarity Testing
3. Model Fitting and Optimization
4. Residual Diagnostics
5. Forecasting

---

## Data Collection
Historical stock prices were retrieved using Yahoo Finance (`yfinance`) for both companies:
- Ubisoft (ticker: `UBI.PA`)
- Take-Two Interactive (ticker: `TTWO`)  
The time frame extended up to January 12, 2025.

---

## Stationarity Testing
### Augmented Dickey-Fuller (ADF) Test:
- **Ubisoft**: Stationarity achieved after differencing once (d=1).  
- **Take-Two Interactive**: Stationarity achieved after differencing once (d=1).  

In both cases, **p-value < 0.05** indicated that the transformed series was stationary.

---

## Model Fitting
### Ubisoft
- **ARIMA Model**: Final order (1, 1, 1) selected using `auto_arima`.
- **SARIMAX Model**: Incorporated seasonality with SARIMAX(1, 1, 1)(1, 0, 1, 12).

### Take-Two Interactive
- **ARIMA Model**: Final order (2, 1, 2) selected after AIC/BIC optimization.
- **SARIMAX Model**: Seasonal order SARIMAX(2, 1, 2)(0, 1, 1, 12).

---

## Residual Diagnostics
Residuals for both Ubisoft and Take-Two Interactive showed:
- **White Noise**: Residuals were normally distributed.
- **Uncorrelated Residuals**: Confirmed with the Ljung-Box test (p-value > 0.05).

---

## Forecasting
### Ubisoft
- 30-day forecast generated using SARIMAX.
- **Visualization**: Actual vs Predicted values plotted with confidence intervals for future forecasts.

### Take-Two Interactive
- 30-day forecast generated using SARIMAX.
- **Visualization**: Similar methodology applied, showing strong predictive performance for seasonal trends.

---

## Comparative Insights
- **Ubisoft**: Seasonality was a significant factor, with stronger SARIMAX performance.
- **Take-Two Interactive**: Exhibited higher variability, and ARIMA captured the trends reasonably well.

---

## Limitations
1. **Ubisoft**: Sensitive to market shocks due to limited stock volume.
2. **Take-Two Interactive**: Volatility in the gaming sector affects model accuracy.
3. External factors (e.g., earnings reports) are not incorporated.

---

## Future Work
1. Explore hybrid models (e.g., ARIMA + GARCH) for volatility modeling.
2. Incorporate external regressors like economic indicators or market indices.
3. Extend forecasts to include confidence intervals for long-term projections.

---

## References
- Statsmodels documentation
- PMDARIMA for automated ARIMA
- Yahoo Finance API for data collection
