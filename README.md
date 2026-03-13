# AI Demand Forecasting for Online Grocery Platforms

## Overview

This project builds a machine learning pipeline to forecast grocery demand using the Instacart Online Grocery Shopping Dataset.

The goal is to understand customer demand patterns and predict future order volume to support inventory planning, warehouse staffing, and delivery operations.

The analysis uses 32M grocery transactions and applies machine learning and time-series forecasting techniques.

---

## Dataset

Source: Instacart Online Grocery Shopping Dataset (Kaggle)

Tables used:

- orders.csv
- order_products__prior.csv
- products.csv
- aisles.csv
- departments.csv

The dataset contains information about:

- order time
- product categories
- reorder behavior
- department demand patterns

---

## Project Workflow

### 1. Data Cleaning

Loaded and merged multiple Instacart tables to create a transaction-level dataset.

Key steps:

- handle missing values
- merge orders and product tables
- rename columns for clarity
- create master dataset

Notebook: 01_data_loading_cleaning.ipynb

---

### 2. Feature Engineering

Created features used by machine learning models:

- hour of day
- day of week
- weekend indicator
- cyclical hour encoding
- department encoding
- log demand transformation

Notebook:02_feature_engineering.ipynb

---

### 3. Demand Analysis

Explored demand patterns across time and product categories.

Visualizations include:

- demand by hour
- demand by weekday
- top departments by demand
- department-hour demand heatmap

Key insight:
Demand peaks during late morning and early afternoon.

Notebook:03_demand_analysis.ipynb

---

### 4. Random Forest Model

Built a baseline machine learning model to predict demand.

Target variable:
log-transformed demand

Evaluation metrics:

- MAE
- RMSE

Notebook:04_random_forest_model.ipynb

---

### 5. XGBoost Model

Improved forecasting accuracy using gradient boosting.

Results:

Best Model: XGBoost

Example performance:

MAE ≈ 523  
RMSE ≈ 1555

Key drivers of demand:

1. Hour of day
2. Department category

Notebook:05_xgboost_model.ipynb

---

### 6. Time-Series Analysis (Prophet)

Applied Prophet to analyze demand seasonality patterns.

Insights:

- daily demand cycles
- weekly demand variation
- peak demand windows

Notebook:06_prophet_forecasting.ipynb

---

## Key Insights

Demand Patterns

- Peak demand occurs between **10 AM – 2 PM**
- Overnight demand is very low
- Produce and dairy drive the highest order volume

Demand Drivers

Most important factors influencing demand:

- time of day
- product department

Operational Implications

These forecasts can support:

- inventory replenishment
- warehouse staffing
- delivery capacity planning

---

## Technologies Used

Python  
Pandas  
NumPy  
Scikit-learn  
XGBoost  
Prophet  
Matplotlib  
Seaborn  

---

## Project Structure
instacart-demand-forecasting/

notebooks/
01_data_loading_cleaning.ipynb
02_feature_engineering.ipynb
03_demand_analysis.ipynb
04_random_forest_model.ipynb
05_xgboost_model.ipynb
06_prophet_forecasting.ipynb

data/
cleaned_orders_products.csv
processed_demand_data.csv

README.md


---

## Future Improvements

Possible improvements include:

- integrating weather data
- adding promotion and pricing signals
- forecasting demand at the product level
- building a real-time demand prediction system

---

## Author

Data Science / Supply Chain Analytics Project

Focused on demand forecasting and operational analytics.
