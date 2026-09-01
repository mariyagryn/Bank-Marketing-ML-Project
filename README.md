# Bank Term Deposit Prediction using Machine Learning

## Project Overview

This project focuses on predicting whether a bank client will subscribe to a term deposit based on demographic, campaign and economic characteristics.

The task is formulated as a binary classification problem.

The goal is to build and compare several machine learning models and select the best performing approach.

---

## Dataset

The dataset used in this project is the Bank Marketing dataset from UCI Machine Learning Repository.

The data contains information about:
- client characteristics;
- previous marketing campaign results;
- contact information;
- economic indicators.

Target variable:

`y` - whether the client subscribed to a term deposit.

Classes:
- yes
- no


---

## Project Workflow

The project includes the following stages:

1. Exploratory Data Analysis (EDA)
2. Feature engineering
3. Data preprocessing
4. Model training
5. Model comparison
6. Hyperparameter optimization
7. Feature importance analysis
8. SHAP interpretation
9. Error analysis


---

## Models Used

The following classification models were trained:

- Logistic Regression
- k-Nearest Neighbors
- Decision Tree
- XGBoost


---

## Model Optimization

For XGBoost hyperparameter tuning two approaches were used:

- RandomizedSearchCV
- Hyperopt Bayesian Optimization


---

## Evaluation Metrics

Models were evaluated using:

- ROC-AUC
- Accuracy
- Precision
- Recall
- F1-score


ROC-AUC was selected as the main metric because the dataset contains imbalanced classes and the model should evaluate the ability to distinguish between positive and negative cases.


---

## Results

The best performance was achieved by XGBoost after hyperparameter optimization.

The best ROC-AUC score:

0.956


---

## Model Interpretation

Feature importance and SHAP analysis were performed to understand which features have the biggest influence on model predictions.

The most influential features included:

- duration
- nr.employed
- economic indicators


---

## Future Improvements

Possible improvements:

- optimize classification threshold;
- handle class imbalance;
- create additional behavioral features;
- train models without potentially leakage-prone features such as duration.
