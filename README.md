# Credit Risk Modelling: Logistic Regression vs XGBoost

# Overview

This project develops and compares two classification models — Logistic Regression and XGBoost — to predict credit default risk using the German Credit dataset.

A unified preprocessing pipeline was implemented to ensure consistency across models, enabling a fair and reliable comparison of performance.

---

# Objectives

* Predict probability of default (credit risk)
* Compare Logistic Regression and XGBoost performance
* Evaluate the impact of classification thresholds
* Balance business trade-offs between risk and profitability

---

# Key Results

| Model               | AUC        |
| ------------------- | ---------- |
| Logistic Regression | 0.7737 |
| XGBoost             | 0.7708 |

# Best Performing Configuration

* Model: XGBoost (tuned)
* Threshold: 0.4
* Recall: 97.1%
* Accuracy: 76.0%

---

# Key Insights

* Both models demonstrated similar predictive power (AUC ≈ 0.77)
* XGBoost achieved higher recall, making it more effective at detecting defaulters
* Logistic Regression provided a better balance between sensitivity and specificity
* Threshold tuning significantly impacted model performance
* Model complexity did not necessarily lead to improved discrimination

---

# Tools & Libraries

* R
* caret
* xgboost
* pROC

---

# Data Preprocessing

* Conerted categorical variables to factors
* Applied one-hot encoding for consistency across models
* Created binary target variable (`credit_risk`)
* Performed 70/30 train-test split

---

# Models Used

# Logistic Regression

* Baseline model
* Interpretable coefficients
* Balanced classification performance

# XGBoost

* Gradient boosting model
* Tuned hyperparameters to reduce overfitting
* Optimized classification threshold

---

# Business Interpretation

In credit risk modeling:

* False Negatives (missed defaulters) → financial loss
* False Positives (rejected good applicants) → lost revenue

This project demonstrates how model selection and threshold tuning must align with a financial institution’s risk appetite.

---

# Project Structure

```
credit-risk-modelling/
│
├── credit_risk_model.Rmd
├── credit_risk_model.html
├── README.md
```

---

# How to Run

1. Open `credit_risk_model.Rmd` in RStudio
2. Click Knit to generate the report

---

# Conclusion

Although XGBoost is a more complex model, it did not significantly outperform Logistic Regression in terms of AUC. The main differences arose from threshold selection and classification behavior.

This highlights the importance of:

* Proper preprocessing
* Model interpretability
* Alignment with business objectives

---

# Author

Bridget Murugi

