# **🏭 Tata Steel Machine Failure Prediction**
Predictive Maintenance using Machine Learning









📌 **Project Overview**

Machine failures in manufacturing industries can lead to significant operational downtime, maintenance costs, and productivity losses.

This project builds a Machine Learning based Predictive Maintenance System that predicts whether a machine will fail based on operational sensor data.

The system helps industries:

✔ Detect failures early

✔ Reduce unexpected downtime

✔ Optimize maintenance schedules

✔ Improve operational efficiency

---

🎯 **Problem Statement**

Develop a machine learning model capable of predicting machine failure events using operational data from industrial machines.

The objective is to enable data-driven predictive maintenance strategies that reduce production disruptions.

---

📊 **Dataset Description**

The dataset contains operational sensor readings and machine condition indicators.

---

**Features**

Feature	Description
| Feature             | Description                    |
| ------------------- | ------------------------------ |
| Type                | Product quality type (L, M, H) |
| air_temperature     | Air temperature (Kelvin)       |
| process_temperature | Process temperature (Kelvin)   |
| rotational_speed    | Machine rotational speed (RPM) |
| torque              | Torque applied to machine      |
| tool_wear           | Tool wear duration             |
| TWF                 | Tool Wear Failure              |
| HDF                 | Heat Dissipation Failure       |
| PWF                 | Power Failure                  |
| OSF                 | Overstrain Failure             |
| RNF                 | Random Failure                 |

Target Variable - machine_failure

| Value | Meaning         |
| ----- | --------------- |
| 0     | No Failure      |
| 1     | Machine Failure |


---

🔧 **Project Workflow**

1️⃣ Data Cleaning

*  Removed unnecessary columns

*  Checked missing values

*  Verified duplicates

*  Standardized column names

2️⃣ Exploratory Data Analysis

*  Performed analysis to understand machine behavior:

*  Distribution analysis

*  Correlation analysis

*  Feature relationships

*  Failure pattern visualization

Key insights identified torque, tool wear, and failure indicators as strong predictors.

---

3️⃣ **Feature Engineering**

Key steps:

✔ Label Encoding for categorical variables

✔ Log Transformation to reduce skewness

✔ StandardScaler for feature scaling

✔ SMOTE for handling class imbalance

✔ Correlation-based dimensionality reduction


--

🤖 **Machine Learning Models**

The following models were implemented and compared:

| Model               | Type                               |
| ------------------- | ---------------------------------- |
| Logistic Regression | Baseline model                     |
| Random Forest       | Ensemble model                     |
| Gradient Boosting   | Boosting model                     |
| XGBoost             | Optimized boosting                 |
| LightGBM            | High-performance gradient boosting |


Hyperparameter tuning was performed using RandomizedSearchCV.

---

📈 **Model Evaluation Metrics**

Models were evaluated using:

*  Accuracy

*  Precision

*  Recall

*  F1 Score

*  ROC-AUC

**Priority Metrics**

Because this is a failure detection problem, the most important metrics are:

✔ **F1 Score

✔ Recall**

These metrics ensure failures are detected while minimizing false alarms.

--- 

🏆 **Best Model**

The LightGBM model with hyperparameter tuning achieved the best performance.

| Metric    | Score     |
| --------- | --------- |
| Accuracy  | 0.993     |
| Precision | 0.762     |
| Recall    | 0.812     |
| F1 Score  | **0.786** |
| ROC-AUC   | 0.950     |

---

**Why LightGBM?**

*  Highest F1 Score

*  Strong precision-recall balance

*  Efficient training

*  Excellent performance on structured datasets

---

🔍 **Model Explainability**

Feature importance analysis revealed the most influential variables:

🔹 HDF (Heat Dissipation Failure)

🔹 OSF (Overstrain Failure)

🔹 PWF (Power Failure)

🔹 TWF (Tool Wear Failure)

🔹 Torque

🔹 Tool Wear

These parameters represent critical indicators of machine stress and operational risk.

---

🚀 **Model Deployment Capability**

The trained model was saved using joblib for future deployment.

Example workflow:

```
Load Model
      ↓
Input Sensor Data
      ↓
Predict Machine Failure
      ↓
Trigger Maintenance Alert

```

This demonstrates how the model can be integrated into predictive maintenance systems.

---

📂 **Project Structure**

```
Machine-Failure-Prediction
│
├── data
│   ├── train.csv
│   └── test.csv
│
├── notebooks
│   └── machine_failure_prediction.ipynb
│
├── models
│   └── machine_failure_lightgbm_model.pkl
│
├── images
│   └── visualizations
│
└── README.md
```

---

🛠️ **Technologies Used**

*  Python

*  Pandas

*  NumPy

*  Scikit-learn

*  XGBoost

*  LightGBM

*  Matplotlib

*  Seaborn

---

📌 **Business Impact**

The predictive maintenance system helps industries:

✔ Prevent unexpected machine breakdowns

✔ Reduce production downtime

✔ Lower maintenance costs

✔ Improve machine reliability

✔ Enable data-driven maintenance decisions

---

🔮 **Future Improvements**

Potential enhancements:

*  Real-time monitoring using IoT sensors

*  Model deployment using REST APIs

*  Continuous model retraining with streaming data

*  Integration with industrial monitoring systems

---

👨‍💻 **Author**

Sagar Jain


Machine Learning | Data Science | Predictive Analytics

---

⭐ If you find this project useful, consider starring the repository.
