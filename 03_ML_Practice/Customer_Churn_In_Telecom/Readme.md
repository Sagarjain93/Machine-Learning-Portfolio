# **Telecom Customer Churn Prediction (Machine Learning)**

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/7a95104f-abb1-4155-a909-ac1c51e5bbe8" />

---

**1. Project Overview**

Customer churn is a major challenge for telecom companies because acquiring new customers is significantly more expensive than retaining existing ones.

This project builds a machine learning model to predict whether a customer will churn based on their demographics, service usage, billing information, and contract details.

The goal is to help telecom companies:

*  Identify customers at high risk of churn

*  Implement targeted retention strategies

*  Reduce revenue loss

The final model detects ~90% of churn customers, enabling proactive intervention.

---

**2. Business Problem**

Customer churn leads to significant revenue loss.

If businesses can predict which customers are likely to churn, they can:

*  Offer retention discounts

*  Provide improved customer support

*  Recommend better plans

*  Increase customer loyalty

The objective of this project is to build a predictive model that accurately identifies churn customers before they leave.

---

**3. Dataset Information**

Dataset: Telecom Customer Churn Dataset

*  Initial records: 7043
*  After cleaning: 7032

**Features include:**

```
Customer demographics

Service subscriptions

Billing information

Contract type

Payment method

Tenure
```

**Target variable:**

```
Churn

1 → Customer churned

0 → Customer stayed
```

**Class distribution:**

*  Non-Churn → ~73%

*  Churn → ~27%

This indicates class imbalance, which influenced model design decisions.

---

**4. Data Cleaning**

The following preprocessing steps were performed:

*  Removed customerID (not useful for modeling)

*  Converted TotalCharges to numeric

*  Removed invalid rows

*  Converted categorical variables

*  Standardized column names

*  Checked for missing values and duplicates

**Final dataset shape:**

*  7032 rows × 20 columns

---

**5. Exploratory Data Analysis (EDA)**

EDA was performed to understand the key drivers of customer churn.

**Key Insights**

*  Customers are more likely to churn if they have:

*  Month-to-month contracts

*  Low tenure

*  High monthly charges

*  No tech support

*  No online security

*  Electronic check payments

*  Senior citizen status

These patterns guided feature engineering and model design.

---

**Visualizations** 

**1️⃣ Churn Distribution**

<img width="549" height="393" alt="Churn_Distribution" src="https://github.com/user-attachments/assets/c0185535-736d-4d8f-8d7c-c4edde9f8c25" />

Shows class imbalance in the dataset.

---

**2️⃣ Churn by Contract Type**

<img width="549" height="431" alt="Contract vs Churn" src="https://github.com/user-attachments/assets/495105cc-b33b-43fc-b34d-2be565ec8e81" />


Month-to-month customers have significantly higher churn rates.

---

**3️⃣ Churn by Tenure**

<img width="531" height="393" alt="Tenure vs Churn" src="https://github.com/user-attachments/assets/894fdf98-f2c8-40ea-a6b9-f79119f14d6d" />

Customers with shorter tenure churn more frequently.

----

**4️⃣ Monthly Charges vs Churn**

<img width="540" height="393" alt="Monthly Charges vs Churn" src="https://github.com/user-attachments/assets/cc3d9e54-83ed-4d63-8893-170e51047139" />

Higher monthly charges correlate with increased churn probability.

---

**5️⃣ Correlation Heatmap**

<img width="584" height="472" alt="Correlation Heatmap" src="https://github.com/user-attachments/assets/20fed931-20da-4d4b-a129-549544109f7c" />

Shows relationships between numeric variables.

---

**6. Data Preprocessing**

Several preprocessing steps were required before modeling.

*  Train-Test Split

The dataset was split using Stratified Sampling:

    Train: 80%
    Test: 20%

This preserved the churn ratio in both datasets.

*  Categorical Encoding

    Categorical variables were encoded using:

*  One-Hot Encoding

Feature count increased from:

    19 → 30 features.

*  Feature Scaling

StandardScaler was applied to numerical features to improve logistic regression performance.

Scaling was fitted only on training data to prevent data leakage.

---

**7. Machine Learning Models**

Three models were trained and evaluated.

*  **Logistic Regression** - Strong baseline model for binary classification.

*  **Decision Tree** - Captures nonlinear relationships but prone to overfitting.

*  **Random Forest** - Ensemble model designed to reduce variance and improve stability.

---

**Model Comparison**

| Model               | ROC-AUC | Recall |
| ------------------- | ------- | ------ |
| Logistic Regression | 0.835   | 0.80   |
| Decision Tree       | 0.818   | 0.78   |
| Random Forest       | 0.838   | 0.78   |

Logistic Regression showed strong baseline performance.

---

**8. Cross Validation**

To ensure model stability, Stratified 5-Fold Cross Validation was applied.

Results confirmed that Logistic Regression generalized well while Random Forest initially showed signs of overfitting.

Hyperparameter tuning was then applied.

---

**9. Hyperparameter Tuning**

RandomizedSearchCV was used to optimize model parameters.

Tuned Logistic Regression

Best parameters:

    *  Penalty: L1

    *  C: 0.01

    *  Class weight: balanced

This improved churn recall from:

0.80 → 0.817

---

**10. Threshold Optimization**

Default classification threshold: 0.50

However, for churn problems recall is more important.

Lowering the threshold improved churn detection.

**Optimal threshold selected : 0.40**

**This increased churn recall to approximately 90%.**

---

**11. Final Model Performance**

**Final model: Tuned Logistic Regression**

**Threshold: 0.40**

**Performance metrics:**

| Metric    | Value    |
| --------- | -------- |
| Precision | 0.42     |
| Recall    | **0.90** |
| F1 Score  | 0.58     |
| Accuracy  | 0.65     |

---

**Visualization**

**Confusion Matrix**

<img width="507" height="432" alt="image" src="https://github.com/user-attachments/assets/afbb5908-c12f-4cb5-9a7f-1583f6168a0c" />

---

**ROC Curve**

<img width="536" height="470" alt="image" src="https://github.com/user-attachments/assets/ccbb0618-cb32-4743-96af-a45943ec09d7" />

---

**12. Key Business Insights**

*  The model identifies customers likely to churn with high recall.

*  High-risk churn segments include:

    *  Month-to-month contract users

    *  Customers with low tenure

    *  Customers paying higher monthly charges

    *  Customers lacking tech support services

Companies can use these insights to design targeted retention strategies.

---

**13. Project Workflow**

```
Data Cleaning
        ↓
Exploratory Data Analysis
        ↓
Feature Engineering
        ↓
Model Training
        ↓
Cross Validation
        ↓
Hyperparameter Tuning
        ↓
Threshold Optimization
        ↓
Final Model Evaluation
```

**14. Tech Stack**

*  Python

*  Pandas

*  NumPy

*  Scikit-Learn

*  Matplotlib

*  Seaborn

*  Jupyter Notebook

---

**15. Repository Structure**

```
Telecom-Churn-Prediction
│
├── raw_data
│   
├── churn_model.ipynb
│
├── images
│   ├── churn_distribution.png
│   ├── churn_by_contract.png
│   ├── tenure_vs_churn.png
│   ├── monthly_charges_churn.png
│   ├── correlation_heatmap.png
│   ├── confusion_matrix.png
│   └── roc_curve.png
│
└── README.md
```

---

**16. Future Improvements**

*  Deploy model using Flask or FastAPI

*  Build Power BI churn dashboard

*  Use XGBoost / LightGBM

*  Perform customer segmentation

---

**17. Author**

**Sagar Jain**

**Aspiring Data Analyst / Data Scientist**

