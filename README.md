# Credit Card Customer Churn Analysis

## 1. Project Overview

This is a small Python data analysis project for ACC102 Track 2. The project studies credit card customer churn. The main aim is to help a bank customer retention team understand which customer groups may have a higher risk of leaving.

The project is kept at a student level. It uses clear Python steps, simple visualisations, and two basic classification models. The focus is not to build a perfect machine learning model. The focus is to turn customer data into useful business insight.

## 2. Target User

The target user is a bank customer retention team or a credit card product manager.

This user may want to know:

- which customer groups have higher churn rates;
- whether inactivity and transaction behaviour are related to churn;
- whether a simple model can support early churn screening;
- what practical actions could reduce customer loss.

## 3. Dataset

The dataset used in this project is `credit_card_churn.csv`.

The original dataset is the Kaggle **Credit Card customers** dataset. It includes customer demographic information, credit card relationship information, usage behaviour, and attrition status.

Suggested source to cite in the reflection report:

> Kaggle. Credit Card customers dataset. Available at: https://www.kaggle.com/datasets/sakshigoyal7/credit-card-customers

Data access date used for this project: **26 April 2026**.

The dataset has 10,127 rows and 23 original columns. The target variable is `Attrition_Flag`, which shows whether a customer is an existing customer or an attrited customer.

## 4. Analytical Questions

This project answers four simple questions:

1. What is the overall customer churn rate?
2. Which customer groups have higher churn rates?
3. How are inactivity, contact frequency, and transaction behaviour related to churn?
4. Can a simple model help the bank identify higher-risk customers?

## 5. Python Workflow

The notebook follows this workflow:

1. Import Python libraries.
2. Load the dataset.
3. Check the data shape, data types, missing values, and duplicates.
4. Remove unsuitable columns, including the customer ID and pre-generated Naive Bayes classifier columns.
5. Convert the churn label into a binary variable.
6. Conduct descriptive analysis and churn-rate analysis.
7. Create visualisations for key churn patterns.
8. Build two simple classification models:
   - Logistic Regression
   - Decision Tree
9. Compare the models using accuracy, precision, recall, F1-score, and ROC-AUC.
10. Summarise business insights and recommendations.

## 6. Key Findings

The main findings from the executed notebook are:

- The dataset is imbalanced. Existing customers account for 83.93% of the sample, while attrited customers account for 16.07%.
- Customer inactivity is strongly related to churn risk.
- Lower transaction count and lower transaction amount are linked with a higher chance of churn.
- A higher number of customer contacts may be a warning signal, because it may show service problems or dissatisfaction.
- In the simple model comparison, the decision tree achieved 0.865 accuracy, 0.905 recall, and 0.941 ROC-AUC on the test set. This is useful for screening, but it should not be used as the only basis for business decisions.
- The most important decision tree feature was `Total_Trans_Ct`, which means transaction count is an important warning signal in this analysis.

## 7. Business Recommendations

Based on the analysis, the bank could consider three practical actions:

1. Monitor customers with several inactive months in the last 12 months.
2. Send usage-based offers to customers with declining transaction counts.
3. Review service records for customers with frequent contacts, because these customers may already be dissatisfied.

## 8. Repository Structure

```text
credit-card-churn-analysis/
│
├── README.md
├── requirements.txt
│
├── data/
│   └── credit_card_churn.csv
│
├── notebook/
│   ├── credit_card_churn_analysis_unrun.ipynb
│   └── credit_card_churn_analysis_executed.ipynb
│
└── outputs/
    ├── cleaned_credit_card_churn.csv
    ├── model_results.csv
    ├── churn_distribution.png
    ├── churn_by_income_category.png
    ├── churn_by_card_category.png
    ├── churn_by_inactive_months.png
    ├── churn_by_contacts_count.png
    ├── transaction_count_by_churn.png
    ├── correlation_heatmap.png
    └── decision_tree_feature_importance.png
```

## 9. How to Run the Project

1. Download or clone this repository.
2. Install the required packages:

```bash
pip install -r requirements.txt
```

3. Open the notebook:

```text
notebook/credit_card_churn_analysis_unrun.ipynb
```

4. Run all cells from top to bottom.

The executed version is also provided as:

```text
notebook/credit_card_churn_analysis_executed.ipynb
```

## 10. Limitations

This project has several limitations.

First, the dataset is observational. It can show relationships, but it cannot prove that one factor causes churn. Second, the dataset does not include customer satisfaction comments, complaint text, competitor offers, or service quality records. These factors may also affect churn. Third, the models are simple and mainly used for learning and screening. They should be tested more carefully before any real business use.

