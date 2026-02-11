# Mumbai Rent Price Prediction

## Overview

This project builds a machine learning model to predict residential rental prices in Mumbai based on property characteristics and geographic location.

The goal is to understand the key factors influencing rental prices and develop an accurate predictive model that can assist tenants, property owners, and real estate platforms in estimating fair rental values.

---

## Key Results

* Final Model: **Tuned Random Forest**
* **R²:** 0.865
* **MAE:** ₹15,800
* **RMSE:** ₹40,000
* Cross-validation Mean R²: ~0.79

The model explains **86% of the variance** in rental prices and identifies **property size and location** as the primary drivers.

---

## Highlights

* End-to-end machine learning workflow
* Extensive data cleaning and feature engineering
* Exploratory data analysis with visual insights
* Multiple model development and comparison
* Cross-validation for model stability
* Hyperparameter tuning
* Feature importance and business interpretation

---

## Problem Statement

Rental prices in metropolitan cities vary significantly due to multiple factors such as property size, number of bedrooms, furnishing level, and location.

This project aims to:

* Analyze rental data for Mumbai
* Identify key price drivers
* Build predictive models
* Select the best-performing model based on accuracy and stability

---

## Dataset

**Source:** Kaggle
**Dataset Size:** ~5,000 Mumbai rental listings

The original dataset contained multiple cities (Mumbai, Pune, Delhi).
This project focuses only on **Mumbai** to capture city-specific rental dynamics.

### Features Used

* `house_size_sqft` – Property size
* `bhk` – Number of bedrooms
* `num_bathrooms`
* `latitude`, `longitude` – Geographic location
* `status` – Furnishing level
* `price` – Monthly rent (Target)

---

## Project Workflow

### 1. Data Cleaning & Preparation

* Removed irrelevant and high-missing columns
* Extracted numerical values from text features
* Handled missing values
* Standardized column names
* One-hot encoded furnishing status (Unfurnished as baseline)

---

### 2. Exploratory Data Analysis

Key observations:

* Rental prices are **right-skewed**
* Strong relationships with:

  * Property size
  * BHK
  * Bathrooms
  * Location
* Furnishing has relatively small impact
* Clear geographic clustering of high-value areas

---

## Sample Visualizations



### Price Distribution

<img width="1246" height="470" alt="image" src="https://github.com/user-attachments/assets/182058c8-fc2b-4ad8-83e5-022430d92baf" />


### Actual vs Predicted

<img width="700" height="547" alt="image" src="https://github.com/user-attachments/assets/226a6933-97e3-48a4-863f-60cf3e624fdc" />

### Feature Importance

<img width="825" height="470" alt="image" src="https://github.com/user-attachments/assets/f7a0e6ab-a6a6-4fd1-9c79-c6c0d09ba76a" />

### Price vs House Size 
<img width="691" height="393" alt="image" src="https://github.com/user-attachments/assets/274e1305-5144-4eac-b8b4-8b093a45743a" />


---

## Model Development

### Linear Regression (Baseline)

* R² ≈ 0.72
* Underfitting due to non-linear relationships

### Random Forest

* R² ≈ 0.86

### Cross-Validation

* Mean CV R² ≈ 0.79
* Confirms model stability and generalization

### Hyperparameter Tuning

Best parameters:

* n_estimators = 500
* max_depth = 10
* min_samples_split = 2
* min_samples_leaf = 1

**Final Performance**

* R²: **0.865**
* MAE: ~₹15,800
* RMSE: ~₹40,000

### Gradient Boosting

Tested but did not outperform Random Forest.

---

## Model Comparison

| Model               | R²        |
| ------------------- | --------- |
| Linear Regression   | 0.72      |
| Random Forest       | 0.86      |
| Tuned Random Forest | **0.865** |
| Gradient Boosting   | 0.85      |

**Final Model:** Tuned Random Forest

---

## Feature Importance

| Feature           | Importance |
| ----------------- | ---------- |
| house_size_sqft   | 0.43       |
| longitude         | 0.18       |
| latitude          | 0.14       |
| num_bathrooms     | 0.14       |
| bhk               | 0.10       |
| status (combined) | < 1.5%     |

### Key Insights

* **Property size** is the strongest driver
* **Location** contributes ~32% combined
* Bathrooms and BHK have moderate impact
* Furnishing status has minimal effect

---

## Business Applications

* Rental price estimation for real estate platforms
* Pricing guidance for property owners
* Market analysis for investors
* Fair rent benchmarking for tenants

---

## Model Limitations

The dataset does not include:

* Building age
* Floor level
* Amenities
* Parking availability
* Neighborhood quality

Including these features could further improve performance.

---

## Tools & Libraries

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn

---

## Project Structure

```
Mumbai-Rent-Prediction/
│
├── mumbai_rent_prediction.ipynb
│
├── raw/
│     └── mumbai.csv (optional)
│
├── images/
│   └── visualization files
│
└── README.md
```

---

## Conclusion

This project demonstrates a complete end-to-end machine learning workflow:

* Data cleaning and wrangling
* Exploratory data analysis
* Feature engineering
* Model building and comparison
* Cross-validation and tuning
* Feature importance and business interpretation

The final tuned Random Forest model provides strong predictive performance and actionable insights into the key factors influencing rental prices in Mumbai.

