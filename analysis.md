# Credit Risk Analysis

## Overview of the Analysis

#### Background

Since many people don’t have the cash available to outright purpose expensive items, such as cars or homes, lenders must make good decisions on who they issue loans to. When a lender issues a loan to an individual, there is risk involved for the lender because the expectation is that loan will be repaid. This isn't always the case though, which is why there is risk for the lender. In order to reduce this risk, lenders will use different models to predict whether a borrower is high or low risk based on financial data they have access to. 

#### Analysis Details/Methodology

For this analysis, I used machine learning to analyze a dataset of historical lending activity from a peer-to-peer lending services company to build a model to identify credit worthiness of borrowers. The financial data used for this model included data from over 77,000 loans and provided the following details for each of these loans: loan size, interest rate, borrower income, debt to income ratio, number of accounts, negative marks, total debt, and the status of the loan. We were looking at the data for roughly 75,000 healthy loans and 2,500 unhealthy loans.  

As part of this analysis, I used two different logistic regression models. The first model used the original dataset to train, fit, and predict using LogisticRegression. The second model used oversampling of the data using RandomOverSampler to balance the data.

The steps I followed for this analysis were:
1.	Splitting the data into training and test sets using scikit-learn (sklearn)
2.	Building and training a logistic regression model on the original data 
3.	Building and training a logistic regression model on the oversampled data 
4.	Evaluating each model’s performance and comparing their results 

The end goal of this model was to use machine learning to determine which loans were healthy (low risk for the lender) and which were unhealthy (high risk for the lender) so we could apply the model to future borrowers to reduce a lenders risk of lending money to the wrong borrowers. 

## Results

Machine Learning Model 1: Logistic Regression on Original Dataset
* Balanced Accuracy Score: 0.952
* Accuracy Score: 0.99
* False Positives: 56 - Predicted loan as High Risk but was actually Healthy
* False Negatives: 102 - Predicted as Healthy but were actually High Risk
* Precision Score for Healthy Loan: 1.00
* Precision Score for High Risk Loan: 0.85
* Recall Score for Healthy Loan: 0.99
* Recall Score for High Risk Loan: 0.91
* F1 Score for Healthy Loan: 1.00
* F1 Score for High Risk Loan: 0.88

Machine Learning Model 2: Logistic Regression on Oversampled Dataset
* Balanced Accuracy Score: 0.993
*	Accuracy Score: 0.99
*	False Positives: 4 - Predicted loan as High Risk but was actually Healthy
*	False Negatives: 116 - Predicted as Healthy but were actually High Risk Precision Score for Healthy Loan: 1.00
*	Precision Score for High Risk Loan: 0.84
*	Recall Score for Healthy Loan: 0.99
*	Recall Score for High Risk Loan: 0.99
*	F1 Score for Healthy Loan: 1.00
*	F1 Score for High Risk Loan: 0.91


## Summary

While both models are good options, the logistic regression model on the oversampled data performed better than the logistic regression model on the original data due to the data being balanced and generating higher accuracy scores. This model will make fewer mistakes when classifying the loans and is the recommended approach.

Overall, the business decision needs to be made whether to use precision or recall by the lender. This will decide whether a lender wants their business model to focus on reducing risk, even if that means turning away good borrowers or if the lender would like to say ‘yes’ more to borrowers, even though they may be taking on more risk of saying yes to an untrustworthy borrower. 
