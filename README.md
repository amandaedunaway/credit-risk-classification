# credit-risk-classification
## Module 20 Challenge: Report

## Overview of the Analysis
The code in credit_risk_classification.ipynb uses the sklearn library to create a logistic regression model to predict loan default risk.
* The given data, lending_data.csv, contains information about individual borrowers, including each borrower's loan amount and interest rate, income, debt, and debt-to-income ratio, number of accounts and derogatory remarks, and finally, whether the borrower defaulted on their loan. 
    * The lending dataset contains information for 77,536 loans, out of which 2,500 are defaulted loans. The smallest loan in the dataset is $5,000, with an average loan amount of $9,806.
    * The dependent variable is a binary variable that is 1 for a borrower that defaulted.
    * The independent variables are the remaining columns of borrower information.
* Before initializing the model, the data is divided into training and testing datasets using `train_test_split()`.
* Next, the logistic regression model is fit to the training data, using `LogisticRegression`.
* Using the model, predictions are made using the testing data, using `.predict()`.
* To evaluate the model's performance, a confusion matrix and classification report, which will be discussed below, is generated.


## Results
The logistic regression model predicts both the healthy and high-risk loans quite well, as outlined by the following results.

* Accuracy score: The accuracy score indicates that the model is correct 99% of the time. However, precision and recall scores will reveal how well it performs for each class prediciton.
* Precision scores: The model has 100% precision in labelling healthy loans and 87% precision in labelling high-risk loans.
* Recall scores: The recall for healthy loans is 100%, and the recall of 95% for high-risk loans leaves little room for false negatives.


## Summary
Overall, the logistic regression model performed well, and I would recommend implementing it for default risk prediction. It detects healthy loans with 100% precision, so we don't have to worry about loans being classified as healthy if they are not. If anything, the model is overly cautious; with the 87% precision of risky loans, the model labels some loans as risky that are not. Finally, given the 95% recall score, there are not very many false negatives; that is, very few of the loans that are actually risky will be labelled as healthy. 