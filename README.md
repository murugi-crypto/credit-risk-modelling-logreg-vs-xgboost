**Credit Risk Modelling: Logistic Regression vs XGBoost**
**Overview**

This project implements an end-to-end credit risk modeling pipeline using the German Credit dataset. It compares two classification approaches — Logistic Regression and XGBoost — to predict loan default risk and evaluates how classification thresholds impact business-relevant outcomes.

The focus is not only on predictive performance, but also on interpretable, decision-oriented modeling for credit risk applications.

**Objective**

Predict probability of credit default (good vs bad clients)
Compare Logistic Regression and XGBoost performance
Analyze the impact of decision thresholds on model behavior
Evaluate trade-offs between sensitivity (risk capture) and specificity (loan approval accuracy)

**Dataset**

Source: German Credit Dataset
Observations: 1000 applicants
Target distribution:
70% Good credit clients (0)
30% Bad credit clients (1)

The target variable was corrected to ensure:
1 = Default (Bad credit risk), 0 = Non-default (Good credit risk)

**Data Preprocessing**

Converted categorical variables into factors
Applied one-hot encoding using caret::dummyVars
Ensured consistent feature space across models
Performed a 70/30 train-test split
Standardized target variable encoding for correct interpretation

**Models Implemented**

1. Logistic Regression
Baseline interpretable model
Provides probabilistic outputs
Suitable for benchmarking and explainability

2. XGBoost (Gradient Boosting)
Non-linear ensemble model
Tuned to reduce overfitting:
max_depth = 3
eta = 0.05
subsample = 0.8
colsample_bytree = 0.8
Trained using xgb.train()

**Threshold Analysis**

To reflect real-world credit decision-making, probability thresholds were tested:

**Threshold	Behavior**

0.5	- Conservative classification (balanced baseline)
0.4 - Best trade-off between sensitivity and specificity
0.3	- High recall but aggressive rejection of good clients

**Model Performance**

Logistic Regression (Best at threshold = 0.4)
Accuracy: ~74%
AUC: ~0.77
Sensitivity: 60.4%
Specificity: 80.4%
Balanced Accuracy: 70.4%

XGBoost (Tuned, Best at threshold = 0.4)
Accuracy: ~74–75%
AUC: ~0.77
Sensitivity: 57.3%
Specificity: 83.3%
Balanced Accuracy: 70.3%

**Key Insights**

Both models achieved similar predictive power (AUC ≈ 0.77)
Logistic Regression performed slightly better in capturing defaulters
XGBoost performed better in protecting good clients
Model performance is highly sensitive to classification threshold selection
The optimal operating point for this dataset is threshold = 0.4

**Business Interpretation**

In credit risk modeling:

False Negatives (missed defaulters) → direct financial loss
False Positives (rejecting good clients) → lost revenue opportunity

This project demonstrates that:

Model selection alone is insufficient — decision thresholds are equally critical in aligning predictions with business risk appetite.

**Conclusion**

Despite using a more complex ensemble method, XGBoost did not significantly outperform Logistic Regression in this structured dataset. This highlights that:

Simpler models can perform competitively in credit scoring tasks
Proper preprocessing and feature encoding are crucial
Threshold tuning has a greater operational impact than model complexity

**Tools & Libraries**

R
caret
xgboost
pROC
ggplot2

**Author**

Bridget Murugi
Actuarial Science | Credit Risk Modeling | Data Analytics
