# Industrial Production Forecasting of US Electric & Gas Utilities

This project focuses on analyzing and forecasting the monthly industrial production of electric and gas utilities in the United States from 1939 to 2024.  The data is sourced from the FRED database.

## Dataset

The dataset used is the "Industrial Production: Electric and Gas Utilities" time series from FRED ([link to dataset](https://fred.stlouisfed.org/series/IPG2211A2N)).  The data has been downloaded as a CSV file (`IPG2211A2N.csv`).

## Data Exploration and Preprocessing

The project begins with an exploratory data analysis (EDA), including visualization and preprocessing. Key steps include:

* **Visualization:** Plotting the time series, box plots by month, and polar charts to understand trends and seasonality.
* **Data Transformation:** Logarithmic transformation is applied to stabilize the variance and achieve stationarity, confirmed by the Augmented Dickey-Fuller test.
* **Decomposition:**  Seasonal decomposition is performed to separate the time series into its trend, seasonal, and residual components.



## Model Building and Evaluation

Several time series forecasting models were trained and evaluated:

1. **ARIMA**
2. **SARIMA**
3. **Simple Exponential Smoothing (SES)**
4. **Holt-Winters' Exponential Smoothing (HWES)**
5. **Prophet (by Meta)**
6. **Chronos (amazon/chronos-t5-tiny)**



One-step ahead forecasts were generated for each model, and the following metrics were used for evaluation:


* **MAE (Mean Absolute Error)**
* **RMSE (Root Mean Squared Error)**
* **R-squared (R2)**
* **MAPE (Mean Absolute Percentage Error)**

The results are visualized in a bar chart to compare model performance.

## Results


| Model                         | MAE    | RMSE   | R-squared | MAPE  |
|-------------------------------|--------|--------|-----------|-------|
| ARIMA                        | 2.763 | 3.417 | 0.883    | 0.027  |
| SARIMA                       | 2.906 | 3.548  | 0.871     | 0.028  |
| SES                          | 2.667  | 3.284 |  0.891    | 0.026  |
| HWES                         | 2.637  | 3.252 | 0.895     | 0.026  |
| Prophet                       | 2.640 | 3.236 | 0.897     | 0.026  |
| **Chronos**                  | **1.048** | **1.283** | **0.975** | **0.009** |



## Further Improvements

* **Hyperparameter Tuning:** Optimize the parameters of each model to potentially improve results.
* **Feature Engineering:** Incorporate additional relevant data (e.g., economic indicators, weather data) as exogenous variables.
* **Advanced Models:** Explore other time series forecasting techniques like deep learning models or hybrid approaches.
