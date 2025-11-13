# Walmart Sales Forecasting using XGBoost


## 🚀 Project Overview

This project focuses on forecasting the weekly sales of various departments across 45 different Walmart stores. The goal is to build a reliable machine learning model that can predict future sales based on historical data, store information, and external economic factors. Accurate sales forecasting is crucial for business decisions related to inventory management, staffing, and promotional planning.

This is a time-series forecasting problem that is solved using a regression approach with the powerful XGBoost algorithm.

---

## 📊 Dataset

The dataset used in this project is the **"Walmart Recruiting - Store Sales Forecasting"** competition dataset from Kaggle. It contains historical sales data from 2010-02-05 to 2012-10-26.

-   **Source:** [Walmart Sales Forecast on Kaggle](https://www.kaggle.com/datasets/aslanahmedov/walmart-sales-forecast/data)
-   **Files Used:**
    -   `train.csv`: Contains the core training data (Store, Dept, Date, Weekly_Sales, IsHoliday).
    -   `features.csv`: Contains additional data for each store and date (Temperature, Fuel_Price, CPI, Unemployment, MarkDowns).
    -   `stores.csv`: Contains information about each store (Type, Size).

---

## 🛠️ Tools and Libraries

This project is implemented in Python 3 and utilizes the following libraries:

-   **Data Manipulation:** `pandas`, `numpy`
-   **Data Visualization:** `matplotlib`, `seaborn`
-   **Machine Learning:** `scikit-learn` (for preprocessing), `xgboost` (for the model)

---

##  workflow Project Workflow

1.  **Data Preparation:** The three source files were loaded, merged, and preprocessed. This included handling missing `MarkDown` values and encoding categorical features.

2.  **Advanced Feature Engineering:** A rich set of features were created to capture time-series dynamics, including time-based (month, week), lag (sales from last year), and rolling window (recent trends) features.

3.  **Exploratory Data Analysis (EDA):** The data was visualized to identify key patterns, such as yearly seasonality and the impact of holidays on sales.

4.  **Model Training & Evaluation:** An XGBoost Regressor was trained on a time-based data split. The model's performance was optimized using early stopping and evaluated on an unseen test set.
---

## 📈 Results and Key Findings

The model demonstrated excellent predictive performance and revealed several key insights:

### Model Performance

-   **Mean Absolute Error (MAE):** **$763.70**
    -   *This means that, on average, the model's sales forecast is off by only about $763, which is a very high level of accuracy.*
-   **Root Mean Squared Error (RMSE):** **$1,681.95**

### Key Feature Importances

The model identified the following features as the most influential for predicting sales:
1.  **`Rolling_3`:** The average sales over the last 3 weeks (short-term trend).
2.  **`Sales_Lag_52`:** Sales from the same week in the previous year (yearly seasonality).
3.  **`Rolling_4`:** The average sales over the last 4 weeks.

