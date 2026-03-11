# Machine Learning Practice

This folder contains my hands-on Machine Learning practice projects, where I experiment with datasets, explore data patterns, build models, and improve my understanding of ML workflows.

The goal of this section is to apply machine learning concepts to real-world datasets while strengthening skills in data cleaning, exploratory analysis, feature engineering, model development, and evaluation.

Some projects here evolve into fully polished portfolio projects, which are then moved to the 02_ML_Projects folder.

---

# **Machine Learning Projects**

Below are the key ML projects developed as part of this practice repository.

| Project                                                       | Problem Type           | Model Used              | Key Result         |
| ------------------------------------------------------------- | ---------------------- | ----------------------- | ------------------ |
| **Telecom Customer Churn Prediction**                         | Classification         | Logistic Regression     | ~90% churn recall  |
| **Mumbai Rent Price Prediction**                              | Regression             | Random Forest           | R² = 0.865         |
| **Tata Steel Machine Failure Prediction**                     | Predictive Maintenance | LightGBM                | F1 Score = 0.786   |
| **Zomato Restaurant Clustering & Customer Behavior Analysis** | Clustering + NLP       | Hierarchical Clustering | Silhouette = 0.556 |

---

# **Project Descriptions**

## **Telecom Customer Churn Prediction**

*  Predicts whether a telecom customer will churn using demographic, service usage, and billing data.

*  Key concepts practiced:

    Classification modeling

    Feature engineering

    Cross-validation

    Hyperparameter tuning

    Threshold optimization

    Business interpretation of churn drivers

**Key Result**

*  The model identifies ~90% of churn customers, enabling proactive retention strategies.

---

## **Mumbai Rent Price Prediction**

*  Builds a regression model to estimate residential rental prices in Mumbai using property characteristics and geographic location.

*  Key concepts practiced:

    Regression modeling

    Feature importance analysis

    Model comparison

    Cross-validation

    Hyperparameter tuning

**Key Result**

*  The final Random Forest model explains ~86% of rental price variance.

---

## **Tata Steel Machine Failure Prediction**

*  A predictive maintenance project that predicts machine failures using industrial sensor data.

*  Key concepts practiced:

    Handling class imbalance with SMOTE

    Ensemble models

    Boosting algorithms

    Hyperparameter tuning

    Model evaluation with precision/recall metrics

**Key Result**

*  The LightGBM model achieved the best performance with F1 score of 0.786.

---

## **Zomato Restaurant Clustering & Customer Behavior Analysis**

*  This project segments restaurants using clustering and NLP analysis of customer reviews to uncover patterns in restaurant performance and customer engagement.

*  Key concepts practiced:

    Natural Language Processing (NLP)

    TF-IDF vectorization

    PCA dimensionality reduction

    Clustering algorithms

    Silhouette score evaluation

**Key Result**

*  Hierarchical clustering produced meaningful restaurant segments with Silhouette score ≈ 0.556.

---

# **Skills Demonstrated**

This repository demonstrates practical experience with:

*  Data Cleaning and Wrangling
*  Exploratory Data Analysis (EDA)
*  Feature Engineering
*  Classification Models
*  Regression Models
*  Clustering Algorithms
*  Natural Language Processing (NLP)
*  Model Evaluation and Cross Validation
*  Hyperparameter Tuning
*  Business Insight Generation

--- 

 # **Workflow Followed**
  
The typical workflow used for projects in this folder:

```
Dataset Selection
↓
Data Cleaning & Preparation
↓
Exploratory Data Analysis
↓
Feature Engineering
↓
Model Development
↓
Model Evaluation
↓
Hyperparameter Tuning
↓
Insight Extraction
```

# **Technologies Used**

*  Python
*  Pandas
*  NumPy
*  Scikit-learn
*  Matplotlib
*  Seaborn
*  NLTK
*  LightGBM
*  XGBoost
*  Jupyter Notebook

---

# **Repository Structure**

```
ML_practice
│
├── Telecom_Customer_Churn_Prediction
├── Mumbai_Rent_Price_Prediction
├── Tata_Steel_Machine_Failure_Prediction
├── Zomato_Restaurant_Clustering
│
└── README.md
```

---

**Note**

This folder contains practice and experimental machine learning projects.

For fully structured and portfolio-ready projects, please refer to:

02_ML_Projects → Final Machine Learning Projects
01_End_to_End → Production-style ML Projects

---

# **Author**

Sagar Jain

Aspiring Data Analyst / Data Scientist
Focused on learning Machine Learning through hands-on projects and real-world datasets.


