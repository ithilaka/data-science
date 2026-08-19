# Electricity Demand Forecasting

## Project Overview

This project analyzes historical electricity consumption and weather data to understand demand patterns and develop statistical models for forecasting daily electricity usage.

The project demonstrates an end-to-end forecasting workflow including data cleaning, exploratory data analysis, feature engineering, baseline forecasting, multiple linear regression, and model evaluation.

## Business Problem

Accurate electricity demand forecasting helps utilities and energy planners anticipate future consumption, manage capacity, and understand the factors that influence changes in demand.

The objective of this project is to:

- Identify patterns and seasonality in electricity consumption
- Analyze the relationship between weather and electricity demand
- Develop baseline forecasting models
- Build a statistical regression model
- Compare forecasting performance using multiple accuracy metrics

## Data

Two datasets were used:

1. Historical electricity consumption data
2. Historical weather data

The datasets were combined by date to create a daily modeling dataset.

Important variables include:

- `USAGE_KWH` - Daily electricity consumption
- `TMAX` - Maximum daily temperature
- `TMIN` - Minimum daily temperature
- `PRCP` - Daily precipitation
- `HOURS_RECORDED` - Number of electricity observations recorded during the day

## Exploratory Data Analysis

EDA included:

- Electricity usage distribution
- Daily electricity consumption over time
- Monthly demand patterns
- Seasonal demand analysis
- Temperature vs electricity consumption
- Missing data analysis
- Incomplete-day validation

Daily electricity usage showed a right-skewed distribution with several high-demand periods.

## Feature Engineering

Features created for modeling included:

- Average temperature
- Weekend indicator
- Previous-day electricity demand (`LAG_1`)
- Previous-week electricity demand (`LAG_7`)
- Calendar-based features

## Forecasting Models

### 1-Day Naive Forecast

Today's electricity demand is predicted using the previous day's actual demand.

### 7-Day Seasonal Naive Forecast

Today's electricity demand is predicted using electricity consumption from the same day one week earlier.

### Multiple Linear Regression

A multiple linear regression model was developed using:

- Average temperature
- Precipitation
- Weekend indicator
- Previous-day demand
- Previous-week demand

The regression model explained approximately 60% of the variation in daily electricity demand in the training data.

## Key Statistical Findings

- Temperature was a statistically significant predictor of electricity consumption.
- Weekend status was statistically significant.
- Previous-day electricity demand was a significant predictor.
- Previous-week electricity demand was also a significant predictor.
- Precipitation was not statistically significant in the initial regression model.
- Residual analysis indicated that the linear model had difficulty capturing some extreme high-demand periods.

## Model Evaluation

Forecasting models were evaluated using:

- MAE - Mean Absolute Error
- RMSE - Root Mean Squared Error
- WAPE - Weighted Absolute Percentage Error
- Forecast Bias

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- Scikit-learn
- Jupyter Notebook

## Future Improvements

Potential extensions include:

- Polynomial regression for nonlinear temperature effects
- Additional lag and rolling-average features
- Day-of-week and monthly seasonality
- Holt-Winters exponential smoothing
- SARIMA forecasting
- Machine-learning forecasting models
