
# 🔍 Optimizing Fraud Detection with Machine Learning

This project explores advanced machine learning methods to detect fraudulent financial transactions using real-world, highly imbalanced data from Capital One. The solution leverages XGBoost, Gradient Boosting, and Random Forest classifiers combined with resampling techniques and thorough data preprocessing to improve fraud detection accuracy and reliability.

---

## 📝 Executive Summary

Fraudulent transactions pose a critical risk in the financial sector. Our project used a real-world Capital One transaction dataset (786,363 records, 29 features) to develop models that could identify fraud while minimizing false positives. We tested models with both SMOTE oversampling and RandomUnderSampler techniques, achieving best performance with XGBoost on under-sampled data.

---

## 💡 Problem Statement

Develop a classification model to detect fraudulent transactions in a highly imbalanced dataset. The objective is to improve fraud detection while reducing false positives, helping Capital One secure customer transactions and reduce financial losses.

---

## 🧹 Data Preprocessing

- **Source**: Capital One internal dataset (2016)
- **Rows/Columns**: 786,363 records, 29 features
- **Dropped Columns**: Empty or redundant — `echoBuffer`, `merchantCity`, `posOnPremises`, `recurringAuthInd`, `accountNumber`, etc.
- **Feature Engineering**:
  - Extracted `day` from `transactionDateTime`
  - Created `transactionAmount_availableMoney_ratio`
- **Winsorization**:
  - Handled outliers in `creditLimit`, `availableMoney`, `transactionAmount`, and `currentBalance`

---

## 📊 Exploratory Data Analysis

- Right-skewed distributions in most financial metrics
- Online retail, rideshare, and online gifts are top fraud categories
- Highest fraudulent merchants: Uber, ebay.com, Fresh Flowers
- High fraud risk in POS codes: Contactless (09), Chip without PIN (05)
- Fraud slightly peaks at 1 PM (13th hour)

Visual Dashboard: [View Tableau Dashboard](https://public.tableau.com/app/profile/jani.shariff.shaik/viz/Book4_17144225634350/Dashboard1)

---

## 🧠 Modeling & Techniques

### Data Preparation
- Label encoding for categorical features
- Dropped IDs and customer-specific identifiers
- Split: 80% Train / 20% Test

### Class Imbalance Handling
- **SMOTE** for oversampling (fraud cases increased to match non-fraud)
- **RandomUnderSampler** to reduce non-fraud cases to match fraud

### Models Used
- **Random Forest**
- **Gradient Boost**
- **XGBoost**

---

## 📈 Model Performance

### 📌 With SMOTE (Oversampling)

| Metric     | XGBoost | Random Forest | Gradient Boost |
|------------|---------|----------------|----------------|
| Accuracy   | 0.8381  | 0.9524         | 0.7081         |
| Precision  | 0.0475  | 0.0732         | 0.0287         |
| Recall     | 0.4893  | 0.1743         | 0.5361         |
| F1 Score   | 0.0866  | 0.1031         | 0.0545         |
| ROC AUC    | 0.7447  | 0.5695         | 0.6234         |

### 📌 With RandomUnderSampler (Under-sampling)

| Metric     | XGBoost | Random Forest | Gradient Boost |
|------------|---------|----------------|----------------|
| Accuracy   | 0.7287  | 0.7434         | 0.7337         |
| Precision  | 0.0420  | 0.0424         | 0.0399         |
| Recall     | 0.7477  | 0.7116         | 0.6927         |
| F1 Score   | 0.0796  | 0.0801         | 0.0755         |
| ROC AUC    | 0.8109  | 0.7278         | 0.7136         |

✅ **Best Model**: XGBoost with under-sampling — strong ROC AUC and recall

---

## ⚙️ Hyperparameter Tuning

Tuned XGBoost to improve metrics:
- Slight improvements in Accuracy, Recall, F1
- High ROC AUC maintained
- Confusion matrix showed strong true positive detection

---

## ✅ Recommendations

1. Encourage NFC-based payments over physical card swipes.
2. Increase fraud monitoring during midday peak hours (1 PM).
3. Conduct merchant fraud awareness campaigns.
4. Limit saving of card details to trusted vendors.
5. Promote bank trust through fraud transparency (only 1.5% transactions were fraud).
6. Implement real-time fraud monitoring systems.
7. Offer customizable fraud alerts to customers.
8. Deploy multi-factor authentication for online transactions.

---

## 🔮 Future Scope

- Apply scaling (MinMax, Standardization) and transformations (log, sqrt)
- Explore advanced class balancing methods (e.g., cost-sensitive learning)
- Use model stacking (e.g., XGBoost + Logistic Regression)
- Expand feature engineering and business-driven insights

---

## 🧾 Dataset

Due to proprietary nature, dataset is not publicly available. Refer to the submission package (`transactions.txt`) for internal use.

---

## 👥 Team Members

- Eraam Khan  
- Jani Shariff Shaik  
- Lakshman Kumar Reddy Peddireddy  
- Venkata Nithin Reddy Yerraguntla  

Instructor: **Dr. Erol Ozkan**, University of Texas at Arlington

---

## 🧠 Meetings

Over 15 collaborative team meetings were conducted to finalize the project.

