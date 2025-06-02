# Predict Calorie Expenditure: A Comparative Analysis and Model Development Journey

---

## 📌 Table of Contents

1. [Introduction](#introduction)
2. [Dataset Overview](#dataset-overview)
3. [Notebook Versions: Summary and Differences](#notebook-versions-summary-and-differences)
4. [Model Development and Rationale](#model-development-and-rationale)
5. [Validation Techniques](#validation-techniques)
6. [Key Learnings and Challenges](#key-learnings-and-challenges)
7. [Results and Performance](#results-and-performance)
8. [Future Work and Improvements](#future-work-and-improvements)
9. [Conclusion](#conclusion)
10. [References and Links](#references-and-links)

---

## 1️⃣ Introduction

This project was developed as part of the Kaggle Playground Series S5E5 Competition: **Predict Calorie Expenditure**. The primary goal was to build models that estimate daily calorie expenditure based on various features like age, heart rate, and duration of activity.

This document details my iterative approach, comparing two key versions of my codebase, explaining the reasoning behind each model, and highlighting validation strategies to ensure robust predictions.

---

## 2️⃣ Dataset Overview

- **Source**: Kaggle Playground Series S5E5
- **Training Data**: Features such as HR_Duration, Duration, Temp_HR, Age, BMI, and the target variable `Calories`.
- **Testing Data**: Same features as the training data (excluding `Calories`).

---

## 3️⃣ Notebook Versions: Summary and Differences

### 🔹 Version 1: `predict-calorie-expenditure.ipynb`

- **Goal**: Develop baseline models using LightGBM and RidgeCV, followed by an ensemble blending strategy.
- **Highlights**:
  - LightGBM with Bayesian Optimization for hyperparameter tuning.
  - RidgeCV to complement LightGBM with a linear model.
  - Weighted ensemble combining LightGBM and RidgeCV predictions.

### 🔹 Version 2: `predict-calorie-expenditure-v2.ipynb`

- **Goal**: Expand the modeling pipeline with advanced techniques.
- **Highlights**:
  - Added LassoCV and ElasticNetCV for additional regularization and robustness.
  - Integrated Stacking Regressor for improved blending of models.
  - Implemented a retraining loop using Bayesian Optimization.
  - Enhanced SHAP analysis for feature importance visualization.
  - Emphasized iterative evaluation to prevent overfitting.

---

## 4️⃣ Model Development and Rationale

- **LightGBM**: Chosen for its efficiency, handling of categorical variables, and robustness on tabular data. Bayesian Optimization was used to select the best hyperparameters.
  
- **RidgeCV, LassoCV, ElasticNetCV**: Added for their ability to capture linear relationships and regularize feature coefficients, preventing overfitting.

- **Ensemble Techniques**:
  - Weighted blending combined predictions from different models for improved generalization.
  - Stacking Regressor leveraged multiple models’ strengths, feeding them into a meta-regressor for final predictions.

---

## 5️⃣ Validation Techniques

- **5-Fold Cross-Validation**: Ensured model performance was consistent across different subsets of the training data.
- **Validation Metric**: Root Mean Squared Log Error (RMSLE) aligned with the competition’s evaluation criteria.
- **Early Stopping**: Implemented to halt training if no improvement was observed, preventing overfitting.

---

## 6️⃣ Key Learnings and Challenges

- **Overfitting**: Carefully tuned hyperparameters and used regularization techniques to mitigate.
- **Leaderboard Discrepancy**: Recognized that local validation scores sometimes differ from public leaderboard scores, highlighting the need for strong cross-validation.
- **Feature Engineering**: Explored log transformations and BMI features, though model complexity sometimes outweighed feature engineering gains.

---

## 7️⃣ Results and Performance

- **Public Leaderboard Score**: 0.05906
- **Private Leaderboard Score**: 0.05906 (final official ranking at competition close).
- Notebook validation scores generally aligned but showed slight differences due to train/test splits.

---

## 8️⃣ Future Work and Improvements

- Incorporate additional ensemble methods like weighted voting and stacking with more diverse models (e.g. XGBoost, CatBoost).
- Explore feature selection pipelines and additional data sources.
- Implement robust error analysis and outlier detection.

---

## 9️⃣ Conclusion

This project demonstrates my ability to iterate on model development, apply advanced machine learning techniques, and adapt to real-world challenges like leaderboard discrepancies. The iterative process and comparative analysis across different models highlight my commitment to building robust, deployable solutions.

---

## 🔗 References and Links

- [Kaggle Competition](https://www.kaggle.com/competitions/playground-series-s5e5)
- [Version 1 Notebook (GitHub/Colab Link)](ADD_YOUR_LINK_HERE)
- [Version 2 Notebook (GitHub/Colab Link)](ADD_YOUR_LINK_HERE)
- [My Kaggle Profile](https://www.kaggle.com/shyam136)

---
