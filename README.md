# NDVI-Land-Cover-Classification-
# Summer Analytics 2025 - NDVI Land Cover Classification 🌿

This repository contains my solution for the **Summer Analytics 2025 Hackathon**, hosted by Consulting & Analytics Club (IITG) and GeeksforGeeks.

---

## Problem Overview

The task was to classify land cover types using NDVI time-series data derived from satellite imagery. The challenge involved dealing with:

- Noisy NDVI signals (due to cloud cover and crowdsourced labeling)
- Missing data
- Seasonal vegetation patterns

The goal was to build a **Logistic Regression-based multiclass model** (competition rule) for predicting 6 land cover classes:
Water, Impervious, Farm, Forest, Grass, Orchard.

---

## Solution Approach

- ✅ **Data Imputation:** Median imputation for missing NDVI values.
- ✅ **Noise Reduction:** Applied rolling window smoothing.
- ✅ **Feature Engineering:** Statistical, seasonal, and trend-based features.
- ✅ **Dimensionality Reduction:** PCA (n=5 components).
- ✅ **Polynomial Expansion:** Degree 2 polynomial features.
- ✅ **Model Training:** Logistic Regression with 5-fold Stratified CV.
## Approach Summary

### 1️⃣ Data Preprocessing

- Median imputation of missing NDVI values.
- Rolling window smoothing to reduce short-term noise fluctuations.
- Post-smoothing re-imputation to handle residual missing data.

### 2️⃣ Feature Engineering

- Statistical features: mean, std, min, max, range, skew, kurtosis, quartiles.
- Time-series trend: NDVI slope via linear regression.
- Seasonal features: summer vs winter NDVI averages and difference.

### 3️⃣ Dimensionality Reduction

- Applied PCA (n=5) to compress 27 NDVI columns into orthogonal principal components, reducing multicollinearity and improving feature compactness.

### 4️⃣ Non-Linear Feature Expansion

- Polynomial Features (degree=2) to enhance non-linearity within the logistic regression framework.

### 5️⃣ Model Training

- Scaled features with StandardScaler.
- Logistic Regression with lbfgs solver, multinomial objective.
- 5-fold Stratified Cross-Validation for robust evaluation.

---
---

## Model Performance

- Average CV Accuracy: **~89.4%**

| Fold | Accuracy |
| ---- | -------- |
| 1    | 89.31%   |
| 2    | 90.00%   |
| 3    | 89.69%   |
| 4    | 88.75%   |
| 5    | 89.50%   |

---

## Tools Used

- Python
- Pandas, Numpy, SciPy
- Scikit-learn

---

## Submission File

- `submission.csv` — final predictions for leaderboard evaluation.

---

🎯 **Special thanks to the organizers for this amazing learning experience!**

---

## Contact

Feel free to connect with me on LinkedIn or GitHub 😊
