# energy-consumption-forecasting
Forecasting energy consumption using time series analysis (stationarity, decomposition, SARIMA) in Python.
# Energy Consumption Forecasting

Forecasting energy consumption from a monthly time series, following a complete pipeline of data preparation, stationarity analysis, and statistical modeling.

This project reproduces and documents the tutorial [*Hands-on: Time Series Forecasting*](https://medium.com/data-science-collective/hands-on-time-series-forecasting-43ccbd418c9a) (Data Science Collective, Medium), with the goal of understanding and applying the key steps of a classic forecasting pipeline in Python.

## Goal

Starting from a monthly energy consumption series (144 observations, January 2004 to December 2015), the project aims to:

- explore and clean the data (datetime indexing, missing values),
- analyze trend and seasonality (additive vs. multiplicative decomposition),
- check the statistical assumptions required for modeling (stationarity, autocorrelation),
- apply different transformations to make the series stationary (log, square root, Box-Cox, moving average),
- build a forecasting model (SARIMA) and evaluate its performance.

## Approach

1. **Data loading and exploration** — reading the CSV, renaming columns, descriptive statistics, setting a datetime index.
2. **Trend analysis** — plotting the series, distribution (histogram + KDE), yearly boxplots.
3. **Series decomposition** — additive and multiplicative decomposition (`statsmodels.tsa.seasonal_decompose`), comparing residuals to pick the more suitable model.
4. **Checking statistical assumptions**:
   - stationarity (rolling mean/std, Augmented Dickey-Fuller test),
   - autocorrelation (ACF/PACF plots).
5. **Transforming the series** to make it stationary — log, square root, Box-Cox, simple moving average (SMA) and exponentially weighted moving average (EWMA), re-testing stationarity after each transformation.
6. **Modeling and forecasting** — building a statistical model (SARIMA) on the stationarized series, forecasting and evaluation.

## Tech stack

- Python 3
- pandas, numpy
- matplotlib, seaborn
- statsmodels (`seasonal_decompose`, `adfuller`, ACF/PACF, SARIMA)
- scipy (Box-Cox transformation)
- Jupyter Notebook

## Repo structure

```
energy-consumption-forecasting/
├── data/                # Dataset (dataset.csv)
├── notebooks/           # Analysis and modeling notebook(s)
├── src/                 # Reusable functions (e.g. automated stationarity test)
├── requirements.txt     # Python dependencies
└── README.md
```

## Installation

```bash
git clone https://github.com/<your-username>/energy-consumption-forecasting.git
cd energy-consumption-forecasting
pip install -r requirements.txt
```

## Usage

```bash
jupyter notebook notebooks/energy_consumption_forecasting.ipynb
```

## Source

This project is based on the Medium article: [*Hands-on: Time Series Forecasting — From Data Preparation to Stationarity and Predictive Modeling*](https://medium.com/data-science-collective/hands-on-time-series-forecasting-43ccbd418c9a) by @anello.

## Author

Hugo Phou
