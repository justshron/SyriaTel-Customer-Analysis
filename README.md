## Project Overview
This project aims to predict customer churn for SyriaTel, a telecommunications company. By building a classification model, we identify which customers are at risk of leaving and determine the primary factors driving their dissatisfaction. This allows SyriaTel to implement proactive retention strategies to minimize revenue loss.

## Business Problem
In the highly competitive telecom industry, retaining existing customers is significantly cheaper than acquiring new ones. SyriaTel needs to know:

Which customers are likely to terminate their contracts?

What behaviors (e.g., service calls, usage patterns, plan types) lead to churn?

How can the company intervene effectively?

## Data Summary
The dataset consists of 3,333 entries with 21 features. Key features include:

Usage: Total minutes and charges for day, evening, night, and international calls.

Demographics: State and Area Code.

Plans: Presence of an International Plan or Voice Mail Plan.

Service: Number of calls made to customer service.

Target: Churn (True/False).

## Data Preparation
Dropped Redundant Features: Removed phone number and all charge columns (due to perfect correlation with minutes) to prevent multicollinearity.

Encoding: Transformed categorical variables using One-Hot Encoding.

Scaling: Standardized features for the Logistic Regression model.

## Modeling and Evaluation
I compared two classification models:

Logistic Regression (Baseline): Used class_weight='balanced' to handle the imbalanced dataset.

Decision Tree Classifier (Final Model): Chosen for its superior performance and interpretability.


Shutterstock
Performance Metrics:
Recall (Churn): ~0.79 — The model successfully identifies 79% of all actual churners.

Precision (Churn): ~0.82 — When the model predicts churn, it is correct 82% of the time.

ROC-AUC: ~0.86 — Demonstrating strong ability to distinguish between classes.

## Key Insights
Customer Service Calls: A critical "tipping point" exists at 4 calls; customers reaching this threshold are significantly more likely to churn.

International Plan: Customers with this plan have a disproportionately higher churn rate, suggesting a potential issue with pricing or service quality in that tier.

Day Minutes: High-usage day callers are more volatile, indicating that SyriaTel's most active users are also the most likely to switch providers.

## Recommendations
Automated Intervention: Flag customers reaching their 3rd or 4th service call for immediate follow-up by a senior retention specialist.

Plan Audit: Review the value proposition of the International Plan to compete better with other providers.

Usage Incentives: Offer loyalty rewards or unlimited day-usage bundles to "power users" to increase loyalty.

Install dependencies: pip install -r requirements.txt (including pandas, scikit-learn, seaborn, matplotlib).

Run the Analysis: Open Index.ipynb in Jupyter Notebook or VS Code to view the full pipeline.

├── Data/
│   └── SyriaTel Customer Churn.csv
├── Index.ipynb             # Main analysis and modeling notebook
├── README.md               # Project summary
└── visualisations/         # Saved charts and plots
