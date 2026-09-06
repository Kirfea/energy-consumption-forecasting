# energy-consumption-forecasting
Forecasting energy consumption using time series analysis (stationarity, decomposition, SARIMA) in Python.
# Energy Consumption Time Series Forecasting

A hands-on time series forecasting project analyzing monthly energy consumption data. The project walks through exploratory data analysis, seasonal decomposition, stationarity validation, and multiple transformation techniques to prepare the series for predictive modeling.

## Overview

Energy consumption is inherently time-dependent, shaped by trend, seasonality, and noise. This project builds a solid foundation for forecasting by rigorously testing and satisfying the statistical assumptions required before fitting any predictive model (ARIMA, SARIMA, or otherwise).

## Objectives

- Explore and clean a monthly energy consumption dataset
- Visualize trend, seasonality, and distribution patterns
- Decompose the series (additive vs. multiplicative)
- Validate stationarity assumptions (rolling statistics, ACF/PACF, Augmented Dickey-Fuller test)
- Apply and compare transformation techniques to achieve stationarity
- Lay the groundwork for predictive modeling (ARIMA/SARIMA/LSTM)

## Project Structure

```
├── data/
│   └── dataset.csv              # Raw monthly energy consumption data
├── notebooks/
│   └── time_series_forecasting.ipynb
├── src/
│   └── stationarity.py          # Reusable stationarity testing function
├── README.md
└── requirements.txt
```

## Methodology

1. **Data Loading & Exploration** — load the dataset, assign proper column names, inspect shape, dtypes, and summary statistics.
2. **Data Processing** — convert dates to datetime, set as index, check for missing values.
3. **Trend Analysis** — visualize the raw series, density plots, and yearly box plots.
4. **Decomposition** — compare additive and multiplicative decomposition to isolate trend, seasonality, and residuals.
5. **Stationarity Assumptions** — validate stationarity, autocorrelation, and distribution assumptions using rolling statistics, ACF/PACF plots, and the Augmented Dickey-Fuller (ADF) test.
6. **Transformations** — test log, square root, and Box-Cox transformations, followed by simple/exponential moving average smoothing, and finally log + differencing (trend and seasonality removal) to achieve stationarity.
7. **Next Steps** — the stationary series is ready for predictive modeling with ARIMA, SARIMA, or deep learning approaches (e.g. LSTM).

## Tech Stack

- Python 3.x
- Pandas / NumPy
- Matplotlib / Seaborn
- StatsModels (seasonal decomposition, ADF test, ACF/PACF)
- SciPy (Box-Cox transformation)

## Key Results

- The raw series is non-stationary (ADF p-value ≈ 0.99), with clear trend and seasonality.
- Log, square root, and Box-Cox transformations alone are insufficient to achieve stationarity.
- Simple moving average smoothing achieves stationarity but at the cost of data loss.
- Log transformation combined with first- and second-order differencing successfully stationarizes the series (ADF p-value < 0.05).


