# Kaggle-Playground-Series-S6E1

🧠 Kaggle Playground Series 2026 – Exam Score Prediction

This project is my first participation in the Kaggle Playground Series (2026).
The goal of the competition was to predict students’ exam scores based on demographic, behavioral, and educational features.
The evaluation metric was Root Mean Squared Error (RMSE).

📊 Dataset Overview

The dataset includes the following features:

age

gender

course

study_hours

class_attendance

internet_access

sleep_hours

sleep_quality

study_method

facility_rating

exam_difficulty

🔹 Data Preparation

Initial data exploration included:

Missing value checks

Outlier and noise analysis

Since this is a Playground dataset, the data was relatively clean and required minimal preprocessing.

Encoding strategy:

Ordinal features were encoded numerically

Categorical features such as study_method were encoded numerically instead of One-Hot Encoding, as tree-based models were the primary focus

(OHE was reserved for models where it is strictly necessary, such as neural networks or SVMs.)

🔹 Modeling & Feature Pruning

Initial experiments were conducted using:

XGBoost

LightGBM

CatBoost

Pairwise regression analysis and cross-validation revealed that some features introduced more noise than signal.
As a result, feature pruning was applied to remove low-utility variables.

Final models:

XGBoost

LightGBM

CatBoost

Random Forest

Hyperparameters were optimized using Optuna, with all evaluations performed using Out-of-Fold Cross-Validation.

🔹 Stacking Strategy

To leverage the strengths of each model:

Predictions from the four base models were used as inputs

A Ridge Regression model was trained as a meta-learner

This linear stacking approach provided a stable and interpretable ensemble.

🏁 Results

Public Leaderboard RMSE: 8.727

Best score in competition: 8.572

Final ranking: Top 27%

Considering this was my first Kaggle Playground competition and that training and experimentation were done under connectivity limitations, this result represents a solid baseline and a meaningful learning experience.

📌 Key Takeaways

Tree-based ensembles remain highly effective for tabular data

Feature pruning can be more impactful than aggressive feature engineering

Stacking with a simple linear meta-model often outperforms complex ensembles
