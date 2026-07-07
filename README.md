# Credit Card Fraud Detection

A machine learning project that detects fraudulent credit card transactions using classification models and handles severe class imbalance through SMOTE oversampling

## Overview
Credit card fraud costs billions annually. This project develops a Random Forest classifier to detect fraudulent transactions, addressing the challenge of extreme class imbalance (580 : 1 legitimate to fraudulent transactions).

### Problem Statement
Traditional rule-based fraud detection systems:
- Generate excessive false positives
- Cannot adapt to evolving fraud patterns

### Solution
A machine learning approach that:
- Achieves 88% recall - catches 88 out of every 100 frauds
- Maintains 87% precision - minimizes customer friction

---

## Key Results
- Recall: 88%
- Precision: 87%
- F1-Score: 0.87

---

## Dataset
- **Source**: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- **Time Period**: 2 days cardholder transactions (September 2013)
- **Size**: 284,807 transactions
- **Features**: 30 (Time + 28 PCA-transformed features + Amount)

---

## Methodology:
1. **Exploratory Data Analysis**:
   - Identified class imbalance
   - Discovered fraud patterns (2-4 AM spike in fraud rate)
   - Analyzed amount distributions (fraud concentrated in small amount transactions)
  
2. **Data Preprocessing**:
   - Train-test split: 80-20 stratified split
   - Imbalance handling with SMOTE
  
3. **Model Selection**:
   - Tested 5 classification algorithm (Random Forest, Logistic Regression, Decision Tree, KNN, SVC)
   - Chose Random Forest with the best performance
  
4. **Hyperparameter Tuning**:
   - Method: RandomSearchCV followed by GridSearchCV
   - Optimization metric: Recall (prioritize catching fraud)
   - Parameters Tuned: n_estimators, max_depth, min_samples_split
   - Result: baseline parameters already optimal
  
5. **Evaluation**:
   - Metrics: Recall, F1-Score, Precision
   - Focus: Recall for catching fraud and precision to avoid false alarms
