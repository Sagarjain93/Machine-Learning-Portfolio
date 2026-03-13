# 🪙 Gold Price Forecasting — Time Series Analysis & Machine Learning

## 📌 Project Overview

This project focuses on forecasting **daily gold prices** using historical market data and comparing multiple modeling approaches ranging from **simple baseline methods to advanced deep learning models**.

The objective is to evaluate whether complex models such as **ARIMA, XGBoost, and LSTM** can outperform a simple **naive baseline model** in predicting short-term gold price movements.

The project implements a **complete end-to-end time series forecasting pipeline**, including:

* Data preprocessing
* Exploratory Data Analysis (EDA)
* Statistical testing
* Time series modeling
* Machine learning modeling
* Deep learning modeling
* Model evaluation and comparison

---

# 📊 Dataset Information

| Feature | Description             |
| ------- | ----------------------- |
| Date    | Trading date            |
| Price   | Gold closing price      |
| Open    | Opening price           |
| High    | Highest price           |
| Low     | Lowest price            |
| Volume  | Trading volume          |
| Chg%    | Daily percentage change |

**Dataset Size**

* **Rows:** 3,104 daily observations
* **Time Range:** 2014 – 2026

---

# ⚙️ Tech Stack

### Programming

* Python

### Data Analysis

* Pandas
* NumPy

### Visualization

* Matplotlib
* Seaborn

### Time Series Modeling

* Statsmodels (ARIMA)

### Machine Learning

* XGBoost

### Deep Learning

* TensorFlow / Keras (LSTM)

---

# 🔎 Exploratory Data Analysis (EDA)

EDA was conducted to understand **trend behavior, distribution patterns, and correlations** within the dataset.

## Price Distribution



Insight:

* Right-skewed distribution
* Majority of prices between ₹25,000 – ₹60,000

---

## Correlation Heatmap

![Correlation Heatmap](images/correlation_heatmap.png)

Insight:

* **Price, Open, High, Low are highly correlated**
* Volume shows moderate correlation
* Daily percentage change behaves independently

---

## Gold Price Trend Over Time

![Gold Price Trend](images/gold_price_trend.png)

Insight:

* Strong long-term upward trend
* Rapid price increase observed after 2020

---

# 📉 Time Series Analysis

### Stationarity Test

Augmented Dickey-Fuller (ADF) Test

Result:

* **ADF Statistic:** 6.0155
* **p-value:** 1.0

Conclusion:

The series is **non-stationary**, therefore **first-order differencing** was applied before ARIMA modeling.

---

# 🤖 Modeling Approaches

Several models were implemented and compared.

## 1️⃣ Naive Baseline Model

Assumption:

```
Tomorrow's price = Today's price
```

This simple benchmark is extremely important in time-series forecasting.

---

## 2️⃣ ARIMA Model

Models tested:

* ARIMA(1,1,0)
* ARIMA(0,1,1)
* ARIMA(1,1,1)

Best model selected based on **AIC score**.

Evaluation performed using **rolling (walk-forward) forecasting**.

---

## 3️⃣ XGBoost Model

Feature engineering included:

* Lag features
* Rolling mean
* Rolling standard deviation

Features used:

* lag_1
* lag_7
* lag_30
* rolling_mean_7
* rolling_std_7
* rolling_mean_30
* rolling_std_30

---

## 4️⃣ LSTM Deep Learning Model

LSTM was trained using a **30-day sliding window sequence**.

Architecture:

```
LSTM Layer (50 units)
↓
Dropout (0.2)
↓
Dense Layer
```

---

# 📊 Model Comparison

| Model          | MAE     | RMSE    | MAPE      |
| -------------- | ------- | ------- | --------- |
| Naive Baseline | **553** | **869** | **0.63%** |
| Rolling ARIMA  | 554     | 870     | 0.63%     |
| Log-ARIMA      | 554     | 870     | 0.63%     |
| LSTM           | 1,618   | 2,371   | 1.73%     |
| XGBoost        | 23,243  | 30,868  | 24.0%     |

---

# 📉 Model Comparison Visualization

![Model Comparison](images/model_comparison.png)

---

# 📈 Actual vs LSTM Forecast

![Actual vs LSTM](images/lstm_forecast.png)

---

# 🏆 Final Model Selection

The **Naive Baseline model achieved the lowest forecasting error**, outperforming all advanced models including ARIMA, XGBoost, and LSTM.

This suggests that gold prices exhibit **strong persistence and random-walk-like behavior**, where the most recent price already contains most of the predictive information.

---

# 💡 Key Insights

* Gold prices show **strong upward long-term trends**
* Time series exhibits **random walk characteristics**
* Complex models **did not outperform the naive baseline**
* Machine learning models struggled to extrapolate strong trends
* LSTM captured the trend but still had higher error

---

# 📚 Key Learnings

* Importance of **baseline models in time series forecasting**
* Rolling forecasting is critical for **realistic model evaluation**
* Feature engineering plays a major role in ML time series models
* Deep learning models require **large datasets and complex patterns**

---

# 🚀 Future Improvements

Possible improvements include:

* Incorporating **macroeconomic variables**

  * Inflation
  * Interest rates
  * USD index
* Testing **Prophet forecasting models**
* Implementing **Transformer-based time series models**
* Hyperparameter tuning for XGBoost and LSTM

---

# 📂 Project Structure

```
Gold-Price-Forecasting
│
├── data
│   └── gold_prices.csv
│
├── notebooks
│   └── gold_price_forecasting.ipynb
│
├── images
│   ├── price_distribution.png
│   ├── correlation_heatmap.png
│   ├── gold_price_trend.png
│   ├── model_comparison.png
│   └── lstm_forecast.png
│
└── README.md
```

---

# 👤 Author

**Sagar Jain**

Data Analyst | Machine Learning Enthusiast

---
