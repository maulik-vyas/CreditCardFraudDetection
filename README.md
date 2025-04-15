# Fraud Detection System for Credit Card Transactions

## **Overview:**

This project develops a machine learning model to detect fraudulent credit card transactions, helping banks protect customers and save millions annually. Using a Kaggle dataset with 284,807 transactions (492 frauds, 0.172% fraud rate), I achieved a 0.977 ROC-AUC, 0.844 AUC-PR, and 0.85 recall for fraud detection.

## **Dataset:** 
The [dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) contains transactions made by European cardholders in September 2013 over two days which is highly imbalanced with 492 frauds out of 284,807 transactions. The positive class (frauds) accounts for 0.172% of all transactions.

Features V1 to V28 are principal components from PCA transformation due to confidentiality. Non-PCA features include Time (seconds elapsed since the first transaction) and Amount (transaction amount). The target Class is binary (1 for fraud, 0 for legitimate).

## **Project Details:**

The goal is to predict whether a transaction is fraudulent, a binary classification task. Key steps include:

* **Exploratory Data Analysis (EDA):** Identified correlations (e.g., V14 had a correlation of 0.5425 with fraud).
* **Feature Engineering:** Created Distance_From_NonFraud to capture anomalies.
* **Handling Imbalance:** Applied SMOTE to balance the training data.
* **Model Training:** Used a Random Forest model with tuned hyperparameters (n_estimators=100, max_depth=30, max_features='log2').
* **Evaluation:** Tested on 56,962 samples (98 fraud, 56,864 non-fraud), achieving 0.977 ROC-AUC, 0.844 AUC-PR, and 0.85 recall for fraud at a 0.5 threshold (25 false positives). Adjusted threshold to 0.1, increasing recall to 0.908 (405 false positives).
* **Explainability:** Used LIME to interpret predictions, identifying key features like Distance_From_NonFraud, V10, V12, and V14.
* **Impact:** A cost-benefit analysis showed ~$500,000 in savings by catching 83–89 fraud cases while managing operational costs.

## **Key Achievements:**
* **Model Performance:** 0.977 ROC-AUC, 0.844 AUC-PR, 0.85 recall for fraud detection.
* **Explainability:** LIME revealed critical features like Distance_From_NonFraud and V14.
* **Financial Impact:** Demonstrated ~$500,000 in savings, balancing fraud detection with efficiency.
