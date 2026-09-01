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
  
## Model Performance Comparison

Different classification models were trained and evaluated using the ROC-AUC metric.

The ROC-AUC metric was selected because the task is a binary classification problem with an imbalanced target variable.

| Model | Hyperparameters | Train ROC-AUC | Validation ROC-AUC | Comment |
|---|---|---|---|---|
| XGBoost + RandomizedSearchCV | Optimized parameters | 0.9657 | 0.9560 | Best result after hyperparameter tuning. The model demonstrates strong performance and good generalization. |
| XGBoost + Hyperopt | Bayesian Optimization | 0.9657 | 0.9560 | Similar result to RandomizedSearchCV, confirming the stability of the optimized model. |
| XGBoost | Default parameters | 0.9651 | 0.9494 | Strong nonlinear model with good predictive performance. |
| Logistic Regression | Default parameters | 0.9349 | 0.9429 | Good baseline model. It is simple and interpretable, but cannot capture complex nonlinear relationships. |
| kNN | n_neighbors = 5 | 0.9622 | 0.8774 | Lower validation performance because distance-based methods are sensitive to the structure and scaling of data. |
| Decision Tree | Default parameters | 1.0000 | 0.7402 | The model shows signs of overfitting because it perfectly fits the training data but performs significantly worse on validation data. |

### Final Model Selection

Based on the validation ROC-AUC score, the best model is **XGBoost with hyperparameter optimization**.

Two optimization approaches were applied:

- **RandomizedSearchCV from Scikit-learn**
- **Bayesian Optimization using Hyperopt**

Both approaches achieved almost identical validation ROC-AUC values (~0.956), which indicates that the final model is stable and the selected hyperparameters provide reliable performance.
