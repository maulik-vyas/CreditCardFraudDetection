# Fraud Detection System for Credit Card Transactions

Every bank aims to detect fraudulent transactions to protect their customers, freeze suspicious credit cards, and save millions of dollars annually by preventing financial losses.

Dataset: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud (The dataset is highly imbalanced with 492 frauds out of 284,807 transactions. The positive class (frauds) accounts for 0.172% of all transactions.)

The dataset contains transactions made by credit cards in September 2013 by European cardholders.
This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

The dataset includes numerical input variables resulting from a PCA transformation. Due to confidentiality, the original features are not provided. Features V1, V2, …, V28 are principal components obtained via PCA. The features Time (seconds elapsed since the first transaction) and Amount (transaction amount) are not PCA-transformed. The target variable Class is binary, with 1 indicating fraud and 0 indicating a legitimate transaction.

Project Overview:
The aim of this project is to predict whether a credit card transaction is legitimate or fraudulent, a binary classification task. I conducted exploratory data analysis (EDA) to identify correlations (e.g., V14 had a correlation of 0.5425 with fraud) and engineered features like Distance_From_NonFraud to capture anomalies. To address the class imbalance, I applied SMOTE (Synthetic Minority Oversampling Technique) to balance the training data.

I trained a Random Forest model with tuned hyperparameters (n_estimators=100, max_depth=30, max_features='log2') and evaluated its performance on a test set of 56,962 samples (98 fraud, 56,864 non-fraud). The model achieved a ROC-AUC of 0.977, AUC-PR of 0.844, and a recall of 0.85 for fraud at the default threshold (0.5), with only 25 false positives. I further adjusted the threshold to 0.1, increasing recall to 0.908 but raising false positives to 405, to explore trade-offs.

To ensure transparency, I used LIME (Local Interpretable Model-agnostic Explanations) to explain predictions, revealing that features like Distance_From_NonFraud, V10, V12, and V14 were key drivers of fraud detection. A cost-benefit analysis showed the model could save approximately $500,000 compared to having no fraud detection system, by catching 83–89 fraud cases while managing operational costs.

Key Achievements:
Model Performance: Achieved 0.977 ROC-AUC, 0.844 AUC-PR, and 0.85 recall for fraud detection using Random Forest.
Explainability: Applied LIME to provide insights into fraud predictions, identifying critical features like Distance_From_NonFraud and V14.
Financial Impact: Demonstrated ~$500,000 in savings through a cost-benefit analysis, balancing fraud detection with operational efficiency.
