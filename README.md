# 🛒 AI Demand Forecasting for Online Grocery Platforms

## 📌 Project Overview

This project builds a **machine learning pipeline to forecast grocery demand** using the **Instacart Online Grocery Shopping Dataset**.

The objective is to analyze purchasing patterns and **predict future order demand** to support:

- Inventory planning
- Warehouse staffing
- Delivery capacity management

The analysis processes **32 million grocery transactions** and applies **machine learning and time-series forecasting models**.

---

## 📊 Dataset

**Source:** Instacart Online Grocery Shopping Dataset (Kaggle)

Tables used:

- `orders.csv`
- `order_products__prior.csv`
- `products.csv`
- `aisles.csv`
- `departments.csv`

The dataset contains information about:

- order timestamps
- product categories
- reorder behavior
- department demand patterns

---

## ⚙️ Project Workflow

### 1. Data Cleaning

Merged multiple Instacart tables to create a transaction-level dataset.

Key steps:

- handled missing values
- merged orders and product tables
- renamed columns for clarity
- created master dataset

Notebook:  
`01_data_loading_cleaning.ipynb`

---

### 2. Feature Engineering

Created predictive features used by machine learning models:

- hour of day
- day of week
- weekend indicator
- cyclical encoding of hour
- department encoding
- log demand transformation

Notebook:  
`02_feature_engineering.ipynb`

---

### 3. Demand Analysis

Explored demand patterns across time and product categories.

Visualizations include:

- demand by hour
- demand by weekday
- top departments by demand
- department-hour demand heatmap

**Key insight**

Demand peaks during **late morning and early afternoon**.

Notebook:  
`03_demand_analysis.ipynb`

## Department Demand Heatmap

The heatmap below shows the **average hourly demand across product departments**.

It highlights how demand varies throughout the day across different grocery categories.

Key observations:

- **Produce dominates demand across most hours**
- **Peak demand occurs between 9 AM – 4 PM**
- Dairy & eggs show strong morning demand
- Overnight demand is minimal across all departments

![Department Demand Heatmap](https://github.com/Ayushs10/ai-grocery-demand-forecasting/blob/main/heatmap.png)

---

### 4. Random Forest Model

Built a **baseline machine learning model** to predict demand.

**Target variable**

`log-transformed demand`

Evaluation metrics:

- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)

Notebook:  
`04_random_forest_model.ipynb`

---

### 5. XGBoost Model

Improved forecasting accuracy using **gradient boosting**.

**Best Model:** XGBoost Regressor

Example performance:

| Metric | Value |
|------|------|
| MAE | ~523 |
| RMSE | ~1555 |

**Key demand drivers**

1. Hour of day
2. Product department

Notebook:  
`05_xgboost_model.ipynb`

---

## 📈 Feature Importance

![Feature Importance](https://raw.githubusercontent.com/Ayushs10/ai-grocery-demand-forecasting/main/Feature%20Imp.png)

---

## 📉 Actual vs Predicted Demand

![Actual vs Predicted Demand](https://raw.githubusercontent.com/Ayushs10/ai-grocery-demand-forecasting/main/Actual%20vs%20demand%20graph.png)

---

### 6. Time-Series Forecasting (Prophet)

Applied **Prophet** to analyze demand seasonality patterns.

Insights:

- daily demand cycles
- weekly demand variation
- peak demand windows

Notebook:  
`06_prophet_forecasting.ipynb`

---

## 🔎 Key Insights

### Demand Patterns

- Peak demand occurs between **10 AM – 2 PM**
- Overnight demand is very low
- Produce and dairy drive the highest order volume

### Demand Drivers

Most influential variables:

- time of day
- product department

### Operational Applications

These forecasts can help support:

- inventory replenishment
- warehouse staffing
- delivery capacity planning

---

## 🧰 Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Prophet
- Matplotlib
- Seaborn

---

---

## 🚀 Future Improvements

Possible improvements include:

- integrating weather data
- adding promotion and pricing signals
- forecasting demand at the product level
- building a real-time demand prediction system

---



