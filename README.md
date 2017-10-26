# CreditCardFraudDetection

Using the anonymous data of credit card transactions available on Kaggle. 

The data has about 290000 rows and 31 features. Less than 0.2% of these transactions 
are fradulent. The goal is to learn a model to predict these fradulent transactions. 
This is finding the needle in a haystack problem. 

As a first pass, we train logistic regression and SVM through 
resampling (specifically undersampling) 
method. The parameters of the models are chosen through KFold cross validation to 
give a high recall accuracy (we want to minimize false negatives).

For unseen data, logistic regression and SVM both give over 90% recall accuracy, 
with SVM doing slightly better.

ROC analysis on the test sample gives area under curve = 0.97. The effect of changing 
threshold on the confusion matrix and the precision recall curve is also investigated. 

To do:  Use Anomaly detection algorithm (by modeling joint probability distribution of 
       features)



