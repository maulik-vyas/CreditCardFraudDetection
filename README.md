# CreditCardFraudDetection

Every bank wants to keep an eye on fraud happening to their customers so that they can freeze the credit card for suspicious transactions and save millions of dollars yearly.

About Dataset: This dataset is taken from Kaggle: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The dataset contains transactions made by credit cards in September 2013 by European cardholders.
This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, original features and more background information about the data cannot be provided. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

Aim of the project is to Predict whether any transaction is legitimate or fraudulent. Since this is a binary classification problem, I used Logistic Regression and achieved 0.995 ROC-AUC score.
