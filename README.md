Credit Risk Modelling: Logistic Regression vs XGBoost
Overview

This project builds and compares Logistic Regression and XGBoost models to predict credit default risk using the German Credit dataset. It evaluates model performance alongside classification threshold sensitivity to align predictions with business risk objectives.

The focus is on predictive accuracy, interpretability, and decision-oriented modeling.

Objective
Predict probability of credit default (good vs bad clients)
Compare Logistic Regression and XGBoost performance
Analyze the effect of classification thresholds on model behavior
Evaluate trade-offs between sensitivity and specificity
Dataset
Source: German Credit Dataset
Observations: 1000 applicants
Target distribution:
70% Good credit (0)
30% Bad credit (1)
Target Definition
1 = Default (Bad credit risk)
0 = Non-default (Good credit risk)
Data Preprocessing
Converted categorical variables to factors
Applied one-hot encoding using caret::dummyVars
Ensured consistent feature space across models
Performed 70/30 train-test split
Standardized target encoding
Models
Logistic Regression
Baseline interpretable model
Produces probabilistic outputs
Used as benchmark
XGBoost (Gradient Boosting)
Non-linear ensemble model
Hyperparameters tuned:
max_depth = 3
eta = 0.05
subsample = 0.8
colsample_bytree = 0.8
Trained using xgb.train
Threshold Analysis
Threshold	Behavior
0.5	Balanced baseline
0.4	Best trade-off between sensitivity and specificity
0.3	High recall, aggressive classification
Model Performance
Logistic Regression (Best at threshold = 0.4)
Accuracy: ~74%
AUC: ~0.77
Sensitivity: 60.4%
Specificity: 80.4%
Balanced Accuracy: 70.4%
XGBoost (Best at threshold = 0.4)
Accuracy: ~74–75%
AUC: ~0.77
Sensitivity: 57.3%
Specificity: 83.3%
Balanced Accuracy: 70.3%
Key Insights
Both models achieved similar predictive performance (AUC ≈ 0.77)
Logistic Regression performed slightly better in detecting defaulters
XGBoost performed slightly better in protecting good clients
Performance is highly sensitive to threshold selection
Optimal operating threshold: 0.4
Business Interpretation

In credit risk modelling:

False Negatives (missed defaulters) → financial loss
False Positives (rejecting good clients) → lost revenue

This demonstrates that:

Model selection alone is insufficient — threshold tuning is critical for aligning predictions with business risk appetite.

Project Structure
credit-risk-modelling/
│
├── README.md
├── credit_risk_model.Rmd
├── credit_risk_model.html
How to Run
Clone repository:
git clone https://github.com/yourusername/credit-risk-modelling.git
Open project in RStudio
Install dependencies:
install.packages(c("caret", "xgboost", "pROC", "ggplot2"))
Run and Knit:
Open credit_risk_model.Rmd
Click Knit
Conclusion
Simpler models perform competitively in structured credit datasets
Preprocessing quality is critical
Threshold tuning has greater impact than model complexity
Tools
R
caret
xgboost
pROC
ggplot2
Author

Bridget Murugi
Actuarial Science | Credit Risk Modeling | Data Analytics
