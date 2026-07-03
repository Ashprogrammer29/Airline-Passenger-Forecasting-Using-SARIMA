# Airline-Passenger-Forecasting-Using-SARIMA

## Overview

This project performs end-to-end time series forecasting on the classic AirPassengers dataset using the SARIMA (Seasonal AutoRegressive Integrated Moving Average) model.

Rather than directly training a forecasting model, the project follows a complete Data Science workflow involving exploratory data analysis, statistical testing, feature engineering, model selection, forecasting, and residual diagnostics.

---

## Problem Statement

Forecast future monthly airline passenger demand using historical passenger data collected between 1949 and 1960.

Accurate forecasting can assist airlines in:

- Capacity planning
- Crew scheduling
- Resource allocation
- Demand forecasting
- Operational decision making

---

## Project Workflow

### 1. Exploratory Data Analysis (EDA)

- Visualized monthly passenger trends
- Identified long-term upward trend
- Identified yearly seasonal patterns

---

### 2. Rolling Statistics

Computed:

- Rolling Mean
- Rolling Standard Deviation

Purpose:

- Detect non-stationarity
- Observe changing statistical properties over time

---

### 3. Stationarity Testing

Performed the Augmented Dickey-Fuller (ADF) Test.

Objective:

Determine whether the time series satisfies the stationarity assumption required by ARIMA-based models.

---

### 4. Log Transformation

Applied logarithmic transformation to:

- Stabilize variance
- Reduce multiplicative seasonality
- Compress large fluctuations

---

### 5. Differencing

Applied:

- First-order differencing
- Seasonal differencing

Purpose:

- Remove trend
- Reduce seasonality
- Obtain a stationary series

---

### 6. ACF & PACF Analysis

Used:

- Autocorrelation Function (ACF)
- Partial Autocorrelation Function (PACF)

Purpose:

Estimate suitable values for:

- AR (p)
- MA (q)

---

### 7. Time-Based Train-Test Split

Unlike conventional machine learning datasets, the data was split chronologically:

- Training Set → Historical observations
- Test Set → Future observations

This prevents data leakage during forecasting.

---

### 8. Model Building

Initially trained:

- ARIMA

Observed limitation:

- Unable to model yearly seasonality effectively.

Upgraded to:

- SARIMA

Reason:

The dataset exhibits clear annual seasonal behavior.

---

### 9. Forecast Evaluation

Model performance was evaluated using:

- RMSE (Root Mean Squared Error)

Forecasts closely followed the actual passenger counts while preserving seasonal behavior.

---

### 10. Residual Diagnostics

Performed:

- Residual Plot
- Residual Density Plot
- Residual ACF

Objective:

Verify that residuals behave like white noise, indicating that the model has captured the underlying temporal structure.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- Scikit-learn

---

## Key Concepts Demonstrated

- Exploratory Data Analysis
- Time Series Forecasting
- Stationarity
- Rolling Statistics
- ADF Test
- Log Transformation
- Differencing
- Feature Engineering
- ACF & PACF
- ARIMA
- SARIMA
- Train-Test Split
- Forecast Evaluation
- Residual Analysis

---

## Results

- Successfully identified trend and seasonality within the dataset.
- Converted the series into a stationary form suitable for ARIMA-based modeling.
- Improved forecasting performance by transitioning from ARIMA to SARIMA.
- Produced forecasts that closely matched actual passenger demand.
- Validated model quality using RMSE and residual diagnostics.

---

## Future Improvements

- Hyperparameter tuning using Grid Search
- SARIMAX with external variables
- Prophet comparison
- XGBoost forecasting with lag features
- LSTM-based deep learning forecasting
- Automated model selection
