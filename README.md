![image](https://github.com/user-attachments/assets/b25a9594-97df-400b-9c8b-593cc7bd0466)

# ⚡ PJMW Hourly Energy Use Analysis

This repository contains a time series analysis of PJMW (PJM Western Region) hourly energy usage data. The project involves loading and visualizing the dataset, splitting it into training and testing sets, performing feature engineering, and preparing the data for machine learning forecasting using XGBoost.

---

## 📂 Dataset

The dataset used is `PJMW_hourly.csv`, which contains hourly megawatt (MW) usage with timestamps. This data is typically used for load forecasting and energy consumption analysis.

---

## 📊 Project Workflow

### ✅ Tasks Completed

- Data loading and datetime parsing
- Exploratory data analysis (EDA)
- Visualization of energy use trends
- Splitting data into training and testing sets
- Feature engineering based on datetime index
- Machine learning model training with XGBoost

---

## 📈 Visualizations

### 1. **Full Time Series Overview**
A scatter plot to visualize overall energy usage patterns across the entire dataset.

### 2. **Train/Test Split Visualization**
Shows a clear division of training and test data at `2015-01-01`.

### 3. **Zoomed View**
Focused look at a week of data from January 2010 to inspect short-term trends.

### 4. **Hourly Pattern Boxplot**
Boxplot illustrating how MW usage varies by hour, helping reveal peak consumption hours.

---

## 🧪 Feature Engineering

Datetime-based features are extracted using the following function:

```python
def create_features(df):
    df = df.copy()
    df['hour'] = df.index.hour
    df['dayofweek'] = df.index.dayofweek
    df['quarter'] = df.index.quarter
    df['month'] = df.index.month
    df['year'] = df.index.year
    df['dayofyear'] = df.index.dayofyear
    df['dayofmonth'] = df.index.day
    df['weekofyear'] = df.index.isocalendar().week
    return df


