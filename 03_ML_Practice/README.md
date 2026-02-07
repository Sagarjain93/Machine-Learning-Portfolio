# Mumbai Rent Price Prediction

## Overview

This project builds a machine learning model to predict residential rental prices in Mumbai based on property characteristics and geographic location.

The goal is to understand the key factors influencing rental prices and develop an accurate predictive model that can assist tenants, property owners, and real estate platforms in estimating fair rental values.

---

## Problem Statement

Rental prices in metropolitan cities vary significantly due to multiple factors such as property size, number of bedrooms, furnishing level, and location.
This project aims to:

* Analyze rental data for Mumbai
* Identify the main drivers of rental prices
* Build and evaluate multiple regression models
* Select the best-performing model based on predictive performance

---

## Dataset

Source: Kaggle
The original dataset contained rental listings for multiple cities (Mumbai, Pune, Delhi).
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
* Extracted numerical features from text fields
* Handled missing values
* Standardized column names
* One-hot encoded furnishing status (Unfurnished as baseline)

---

### 2. Exploratory Data Analysis

Key findings:

* Rental prices are **right-skewed**
* Strong relationship between price and:

  * Property size
  * BHK
  * Bathrooms
  * Location
* Furnishing has relatively smaller impact
* Clear geographic clustering of high-value areas

---

### 3. Model Development

#### Linear Regression (Baseline)

* R² ≈ 0.72
* Underfitting observed due to non-linear relationships

#### Random Forest

* Significant improvement
* R² ≈ 0.86

#### Cross-Validation

* Mean CV R² ≈ 0.79
* Confirms model stability and generalization

#### Hyperparameter Tuning

Best parameters:

* n_estimators = 500
* max_depth = 10
* min_samples_split = 2
* min_samples_leaf = 1

Final Performance:

* **R²: 0.865**
* **MAE: ~₹15,800**
* **RMSE: ~₹40,000**

#### Gradient Boosting

Tested but did not outperform Random Forest.

**Final Model: Tuned Random Forest**

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

* **Property size** is the strongest driver of rent
* **Location** has major influence (~32% combined)
* Bathrooms and BHK have moderate impact
* Furnishing status has minimal effect

---

## Business Insights

Rental pricing in Mumbai is primarily driven by:

1. Property size
2. Geographic location
3. Structural features

Furnishing level plays a secondary role compared to size and location.

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
├── │ mumbai_rent_prediction.ipynb
│
├──  raw/
│       └── mumbai.csv   
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

The final Random Forest model provides strong predictive performance and actionable insights into rental price drivers.
