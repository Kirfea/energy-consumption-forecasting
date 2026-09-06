# energy-consumption-forecasting
Forecasting energy consumption using time series analysis (stationarity, decomposition, SARIMA) in Python.
# Energy Consumption Time Series Forecasting

A time series forecasting project analyzing monthly energy consumption data. Covers exploratory data analysis, seasonal decomposition, stationarity validation and transformation techniques to prepare the series for predictive modeling.

## Overview

Energy consumption changes over time, shaped by trend and seasonality. Before fitting a predictive model (ARIMA, SARIMA or otherwise), the series has to satisfy a few statistical assumptions. This project goes through that process step by step.

## Objectives

- Explore and clean a monthly energy consumption dataset
- Visualize trend, seasonality and distribution patterns
- Decompose the series (additive vs multiplicative)
- Test stationarity assumptions (rolling statistics, ACF/PACF, Augmented Dickey-Fuller test)
- Apply and compare transformation techniques to reach stationarity
- Prepare the data for predictive modeling (ARIMA/SARIMA/LSTM)

## Project Structure

```
data/
    dataset.csv               Raw monthly energy consumption data
notebooks/
    time_series_forecasting.ipynb
src/
    stationarity.py           Stationarity testing function
README.md
requirements.txt
```

## Methodology

1. Data loading and exploration: load the dataset, assign column names, inspect shape, dtypes and summary statistics.
2. Data processing: convert dates to datetime, set as index, check for missing values.
3. Trend analysis: raw series plot, density plots, yearly box plots.
4. Decomposition: compare additive and multiplicative decomposition to isolate trend, seasonality and residuals.
5. Stationarity assumptions: rolling statistics, ACF/PACF plots and the Augmented Dickey-Fuller (ADF) test.
6. Transformations: log, square root and Box-Cox transformations, simple/exponential moving average smoothing, then log transformation combined with differencing to remove trend and seasonality.
7. Next steps: once the series is stationary, it can be used for predictive modeling with ARIMA, SARIMA or deep learning approaches such as LSTM.

## Tech Stack

- Python 3.x
- Pandas / NumPy
- Matplotlib / Seaborn
- StatsModels (seasonal decomposition, ADF test, ACF/PACF)
- SciPy (Box-Cox transformation)
