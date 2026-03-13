# Water Potability Classification Project

## Project Overview
This project aims to predict water potability (whether water is safe for human consumption) based on various water quality metrics. Using a dataset of 3,276 water bodies, we implement a full machine learning pipeline including data cleaning, exploratory data analysis, feature engineering, and a comparison of multiple classification algorithms.

## Dataset Description
The dataset contains the following features:
- **pH**: Evaluation of acid-base balance.
- **Hardness**: Capacity of water to precipitate soap.
- **Solids**: Total dissolved solids in ppm.
- **Chloramines**: Amount of Chloramines in ppm.
- **Sulfate**: Amount of Sulfates dissolved in mg/L.
- **Conductivity**: Electrical conductivity of water.
- **Organic Carbon**: Amount of organic carbon in ppm.
- **Trihalomethanes**: Amount of THMs in ͸g/L.
- **Turbidity**: Measure of light-emitting properties of water.
- **Potability**: Target variable (1: Potable, 0: Not Potable).

## Methodology

### 1. Data Preprocessing
- **Missing Value Imputation**: Used **KNN Imputer** (n=7) to estimate missing values in pH, Sulfate, and Trihalomethanes, preserving data distribution better than mean/median imputation.
- **Outlier Removal**: Implemented **K-Means Clustering** to identify and filter out data points that deviated significantly from the main clusters.
- **Feature Scaling**: Applied **StandardScaler** to normalize feature ranges for distance-based and gradient-based algorithms.
- **Class Imbalance**: Utilized **SMOTE** (Synthetic Minority Over-sampling Technique) to balance the target classes during training.

### 2. Models Evaluated
We compared the following models:
- K-Nearest Neighbors (KNN)
- Logistic Regression
- Support Vector Machine (SVM)
- Decision Tree
- XGBoost
- Neural Network (TensorFlow/Keras)

## Key Results
Based on our evaluation, the **Decision Tree** and **XGBoost** models performed exceptionally well on this specific dataset configuration, achieving test accuracies above 97%.

| Model | Test Accuracy | F1-Score (Weighted) |
| :--- | :---: | :---: |
| Decision Tree | 99.2% | 0.99 |
| XGBoost | 97.3% | 0.97 |
| Neural Network | 67.7% | 0.67 |
| SVM | 66.9% | 0.67 |

## Requirements
- Python 3.x
- Pandas, NumPy
- Scikit-learn
- XGBoost
- TensorFlow & Scikeras
- Matplotlib & Seaborn