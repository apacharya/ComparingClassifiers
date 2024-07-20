# Comparing Classifiers

## Objective: 
Predict if a Customer will subscribe to term deposit leveraging a Bank Markering campaign data.**

## Overview: 
In this project, my goal is to compare the performance of the classifiers such as K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines.  I am utilizing the dataset related to bank marketing over the telephone. ROI is to reduce marketing costs by leveraging the primary drivers of subscription and targetting the campaign better.

## Data Overview: 
The data is related with direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be ('yes') or not ('no') subscribed. 
Dataset contains 20 features and 1 target variable.

Our dataset comes from the UCI Machine Learning repository [link](https://archive.ics.uci.edu/ml/datasets/bank+marketing).  The data is from a Portugese banking institution and is a collection of the results of multiple marketing campaigns. This article accompanying the dataset [here](CRISP-DM-BANK.pdf) for more information on the data and features.

### Features

Input variables:
#### bank client data:
1 - age (numeric)
2 - job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')
3 - marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)
4 - education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')
5 - default: has credit in default? (categorical: 'no','yes','unknown')
6 - housing: has housing loan? (categorical: 'no','yes','unknown')
7 - loan: has personal loan? (categorical: 'no','yes','unknown')
#### related with the last contact of the current campaign:
8 - contact: contact communication type (categorical: 'cellular','telephone')
9 - month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')
10 - day_of_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')
11 - duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.
#### other attributes:
12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
14 - previous: number of contacts performed before this campaign and for this client (numeric)
15 - poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')
#### social and economic context attributes
16 - emp.var.rate: employment variation rate - quarterly indicator (numeric)
17 - cons.price.idx: consumer price index - monthly indicator (numeric)
18 - cons.conf.idx: consumer confidence index - monthly indicator (numeric)
19 - euribor3m: euribor 3 month rate - daily indicator (numeric)
20 - nr.employed: number of employees - quarterly indicator (numeric)

Output variable (desired target):
21 - y - has the client subscribed a term deposit? (binary: 'yes','no')


## Algorithms Used for Analysis and Skills displayed

- Explorative Analysis using matplotlib, seaborn
- Modeling using Classifiers - K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines
- Hyperparameter tuning and grid search
- Model Explanation 


## Conclusion

I ran several models to predict the target of whether a customer will subscribe to term deposit or not. Logistic Regressor was the fastest to train and SVM was the slowest.

- All models are performing well with accuracy > ~ 0.84.

- The best fit model materialized by the Decision Tree Classifer achieved highest F1-Score: 0.58 althought its accuracy is acceptably good with 85%. This model does not overfit. 
- Decision tree model has relatively higher recall (0.93) and low precision (0.4). False negatives are missed opportunities where model has missed to predict the customers who actually subscribed. The model does not high False negatives (93% recall for capturing missed opportunities). The only model which reduces False negatives is Decision Tree Classifier and hence can be reported to be the best prediction model for our goal.

- Call duration is the top feature predicting high subscriptions to term deposit. Hence, model indicates that the longer the call duration, there is higher chance for customer to subscribe.
- Number of Employees - quarterly indicator (nr.employed) is the second top feature predicting subscriptions to term deposit indicating that the more the number of employees working and making calls, the more subscriptions we can get.
- Consumer Price Index (CPI) is third top feature which indicates that higher the CPI, the higher the subscription rate

## Recomendation

Keep motnitoring the modeling results as we add more data and monit for drifts in results
Add more data from more creative campaigns and iteratively refresh the model on new data to get latest and deeper perspetives of customers intending to subscribe

