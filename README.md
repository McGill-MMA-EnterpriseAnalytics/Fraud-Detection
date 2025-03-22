# AI-Driven Fraud Detection System

## Overview

This project focuses on building a robust **AI-powered fraud detection system** tailored for the **banking industry**, where fraudulent transactions are both costly and complex. Traditional rule-based models tend to overflag legitimate activities, causing customer dissatisfaction and inefficiencies. Our model addresses this by integrating **machine learning**, **ensemble learning**, **feature explainability**, and **causal inference** to minimize false positives while maximizing fraud capture.

## Goals

- **Detect fraudulent transactions** with high precision and recall.
- **Reduce false positives** to improve user experience and avoid unnecessary intervention.
- **Enhance operational efficiency** via automation and explainability.
- **Comply with regulatory requirements** (e.g., GDPR, AML policies).

## Stakeholders

- **Financial Institutions**: Banks, credit unions, fintechs.
- **Risk & Compliance Teams**: Monitoring and reporting.
- **Data Science Teams**: Model development and deployment.
- **End-users**: Customers impacted by fraud protection.

## Dataset

- 📦 **Source**: Kaggle (*suspicion of being a synthetic dataset*)  
- 🧾 **Records**: 200,000 transactions  
- 🔍 **Target Variable**: `Is_Fraud`  
- ✅ Cleaned: No missing values or duplicates

## Key Insights

- **Fraud Rate**: ~7% of all transactions
- **High-Risk Features**:  
  - `Transaction_Amount` (Corr = 0.94 with fraud)  
  - `Transaction_Day` (Thu & Fri peaks)  
  - `Device_Type` (Mobile, POS)
- **Low-Risk Features**: `Age`, `Account_Balance`

## Data Preprocessing

- **Time Binning**: Morning, Afternoon, Evening, Night
- **Encoding**:
  - One-Hot: Low-cardinality categorical variables
  - Frequency/Label: Medium cardinality
  - K-Fold Target Encoding: High-cardinality variables
- **Imbalance Handling**: SMOTETomek

## Models Used

| Model            | Notes                     |
|------------------|---------------------------|
| Logistic Regression | Suspiciously perfect      |
| KNN              | Overfitting possible      |
| Random Forest    |                           |
| XGBoost          |                           |
| LightGBM         |                           |
| Stacking (XGB + LGBM ➝ LR) | Final model               |

**Note**: Despite perfect training scores, test set metrics show:
- **Precision**: 74%
- **Recall**: 53%

This suggests some **overfitting**, and further tuning or real-time validation is needed.

## Feature Importance & Explainability

- **Random Forest + SHAP Analysis** reveal:
  - `Transaction_Amount` is the strongest fraud predictor.
  - `Transaction_Month` suggests seasonal fraud patterns.
  - `Transaction_Device` and `Merchant_Category` also important.

## Unsupervised Learning

**Customer Segmentation via Clustering**:
- Grouped customers into 4 behaviorally distinct clusters (e.g., VIPs, Savers, Young Professionals).
- Enables **targeted fraud policies** and **personalized marketing**.

## Business Impact

- **Fraud Loss Reduction**: Early detection and prevention.
- **Operational Efficiency**: Automation reduces manual investigation time.
- **Improved Customer Experience**: Lower false alarms.
- **Regulatory Compliance**: Supports AML monitoring frameworks.

## Team Members

| Name           | Role                    | GitHub                    |
|----------------|-------------------------|---------------------------|
| Kartik Joshi   | Modeller                | [kartikjoshi2077](https://github.com/kartikjoshi2077) |
| Qian Zhao      | Data Handling           | [qzhao-mma7](https://github.com/qzhao-mma7) |
| Phoebe Gao     | Modeller & Analyst      | [JenniferYang704](https://github.com/JenniferYang704) |
| Mengyue Yang   | Data Analyst            | [PiG-9](https://github.com/PiG-9) |
| Palvi Sharma   | Project Manager         | [Palvi-Sharma](https://github.com/Palvi-Sharma) |
