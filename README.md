**Credit Risk Modelling: Logistic Regression vs XGBoost**
***Overview***

This project implements an end-to-end credit risk modeling pipeline using the German Credit dataset. It compares Logistic Regression and XGBoost models to predict loan default risk and evaluates how classification thresholds impact business-relevant outcomes.

The focus is on predictive performance as well as interpretable, decision-oriented modeling for credit risk applications.

***Objective***
Predict probability of credit default (good vs bad clients)
Compare Logistic Regression and XGBoost performance
Analyze the impact of classification thresholds on model behavior
Evaluate trade-offs between sensitivity (risk capture) and specificity (loan approval accuracy)

***Dataset***
Source: German Credit Dataset
Observations: 1000 applicants
Target distribution:
70% Good credit clients (0)
30% Bad credit clients (1)

The target variable is defined as:

1 = Default (Bad credit risk)
0 = Non-default (Good credit risk)

***Data Preprocessing***
Converted categorical variables into factors
Applied one-hot encoding using caret::dummyVars
Ensured consistent feature representation across models
Performed a 70/30 train-test split
Standardized target variable encoding

***Models Implemented***

1. Logistic Regression
Baseline interpretable model
Produces probabilistic outputs
Used as a benchmark model

2. XGBoost (Gradient Boosting)
Non-linear ensemble model
Tuned hyperparameters:
max_depth = 3
eta = 0.05
subsample = 0.8
colsample_bytree = 0.8
Trained using xgb.train
Threshold Analysis

To reflect real-world credit decision-making, probability thresholds were evaluated:

***Threshold	Behavior***
0.5 -	Conservative classification (balanced baseline)
0.4	- Best trade-off between sensitivity and specificity
0.3	- High recall but aggressive rejection of good clients

***Model Performance***
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

***ROC Curve Analysis***
The ROC curve evaluates model discrimination across all classification thresholds.

***Key Insights***
Both models achieved similar predictive power (AUC ≈ 0.77)
Logistic Regression performed slightly better in identifying defaulters
XGBoost performed slightly better in protecting good clients
Model performance is highly sensitive to classification thresholds
The optimal operating threshold for this dataset is 0.4
Business Interpretation

In credit risk modeling:

False Negatives (missed defaulters) lead to financial loss
False Positives (rejecting good clients) lead to lost revenue opportunities

This project demonstrates that:

Model selection alone is insufficient. Decision thresholds are equally critical in aligning predictions with business risk appetite.

Project Structure
credit-risk-modelling/
│
├── README.md
├── credit_risk_model.Rmd
├── credit_risk_model.html

How to Run This Project
Clone the repository:
git clone https://github.com/yourusername/credit-risk-modelling.git
Open the R project or RStudio
Install required packages:
install.packages(c("caret", "xgboost", "pROC", "ggplot2"))
Run the R Markdown file:
credit_risk_model.Rmd
Click “Knit” to generate the HTML report

***Conclusion***

Despite using a more complex ensemble method, XGBoost did not significantly outperform Logistic Regression in this structured dataset.

Key findings:

Simpler models can perform competitively in credit scoring tasks
Proper preprocessing and encoding are critical
Threshold tuning has a greater operational impact than model complexity

***Tools and Libraries***
R
caret
xgboost
pROC
ggplot2
Author

Bridget Murugi
Actuarial Science | Credit Risk Modeling | Data Analytics
