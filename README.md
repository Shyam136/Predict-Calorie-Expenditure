# Predict Calorie Expenditure: Model Development and Comparative Analysis

---

## 📌 Table of Contents

1. [Introduction](#introduction)
2. [Dataset Overview](#dataset-overview)
3. [Notebook Versions: Summary and Differences](#notebook-versions-summary-and-differences)
4. [Model Development and Rationale](#model-development-and-rationale)
5. [Validation Techniques](#validation-techniques)
6. [Results and Performance](#results-and-performance)
7. [References and Links](#references-and-links)

---

## 1️⃣ Introduction

This project was developed for the Kaggle Playground Series S5E5 Competition: **Predict Calorie Expenditure**. The goal was to estimate daily calorie expenditure based on features like heart rate, duration, and age.

This document summarizes my iterative approach, comparing two versions of the notebook and outlining model choices, validation techniques, and key results.

---

## 2️⃣ Dataset Overview

- **Source**: Kaggle Playground Series S5E5
- **Training Data**: Features such as HR_Duration, Duration, Temp_HR, Age, BMI, and the target variable `Calories`.
- **Testing Data**: Same features as the training data (excluding `Calories`).

---

## 3️⃣ Notebook Versions: Summary and Differences

### 🔹 Version 1: `predict-calorie-expenditure.ipynb`

- **Goal**: Develop baseline models using LightGBM and RidgeCV with a basic ensemble strategy.
- **Key Components**:
  - LightGBM with Bayesian Optimization.
  - RidgeCV linear model.
  - Weighted blending to combine predictions.

### 🔹 Version 2: `predict-calorie-expenditure-v2.ipynb`

- **Goal**: Enhance modeling pipeline with more advanced techniques.
- **Key Components**:
  - Added LassoCV and ElasticNetCV for regularization.
  - Stacking Regressor to combine multiple models.
  - Retraining loop using Bayesian Optimization for hyperparameter tuning.
  - SHAP analysis for feature importance visualization.

---

## 4️⃣ Model Development and Rationale

- **LightGBM**: Chosen for its speed and performance on tabular data, with hyperparameters optimized via Bayesian Optimization.
  
- **RidgeCV, LassoCV, ElasticNetCV**: Provided linear baseline models with regularization, helping control overfitting.

- **Ensemble Techniques**:
  - Weighted blending combined different models for improved generalization.
  - Stacking Regressor leveraged multiple models’ strengths by feeding them into a meta-regressor.

---

## 5️⃣ Validation Techniques

- **5-Fold Cross-Validation**: Ensured consistency across different data subsets.
- **Validation Metric**: Root Mean Squared Log Error (RMSLE) consistent with competition evaluation.
- **Early Stopping**: Stopped training when performance plateaued.

---

## 6️⃣ Results and Performance

- **Best Public Leaderboard Score**: 0.05906
- **Private Leaderboard Score**: 0.05906 (final official ranking).
- Notebook validation scores closely matched leaderboard scores, reinforcing model stability.

---

## 🔗 References and Links

- [Kaggle Competition](https://www.kaggle.com/competitions/playground-series-s5e5)
- [Version 1 Notebook (GitHub/Colab Link)](https://www.kaggle.com/code/shyam136/predict-calorie-expenditure)
- [Version 2 Notebook (GitHub/Colab Link)](https://www.kaggle.com/code/shyam136/predict-calorie-expenditure-v2)
- [My Kaggle Profile](https://www.kaggle.com/shyam136)

---
