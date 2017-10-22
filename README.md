# CreditCardFraudDetection

Using the anonymous data of credit card transactions available on Kaggle. 

The data has about 290000 rows and 31 features. Less than 0.2% of these transactions 
are fradulent. The goal is to learn a model to predict these fradulent transactions. 
This is finding the needle in a haystack problem. 

As a first pass, we analyse the problem through resampling (specifically undersampling) 
method. From the majority class, we sample at random n examples, where n is the 
number of fraud cases (~500). That gives us a roughly 50-50 ratio to work with. 

We split the data into training set (70 % of 1000) and the test set. 
We train a logistic regression model on the training data,
choosing the regulaization paramter C through KFold cross-validation. 
This parameter is chosen to get a high value for recall (we don't want to miss 
flagging the fradulent transaction) while at the same time making sure that 
F1 score is not too low. 

The model offers a 95.6% recall accuracy on the unseen test data with the F1 score of 0.9. 
When used on the complete data (~290k transactions), the recall accuracy is 96.5% 
however, the F1 score is only 0.02.

ROC analysis on the test sample gives area under curve = 0.97. The effect of changing 
threshold on the confusion matrix and the precision recall curve is also investigated. 

To do: 1) Use advanced classification algorithms such as SVM and random forest. 
       2) Use Anomaly detection algorithm (by modeling joint probability distribution of 
       features)



