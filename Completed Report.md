# Module 12 Report Template

## Overview of the Analysis

The purpose of performing this analysis is to create a model (logistical regression model) that identifies a borrower's creditworthiness by using financial information within a data set that contains historical lending activity. This data was pfovided by a peer-to-peer lending service company.

The data was preped in a binary classification to predict the "Status of a loan" with the following labels: healthy loan "0" and high-risk loans "1". To accurataly make these predicitons, predictive features are included:
Loan Size
Interest Rate
Borrower Income
Debt to Income
Number of Accounts
Derogatory Marks
Total Debt

The data contained information of 77536 borrowers and had imbalanced proportions of healthy loans 75036 and 2500 high risk loans.

To start the creation of the Logistical Regression Model first the data had to be split into training and testing data using the train_test_split module. Then using the the "object creation, fit, predict" set of steps, the logistic regression model was created, then the training data is fitted into the model to teach it. Later, the model was used to predicting the testing data without the key "Status of a loan" to see if it could approach the original data. After the predicitons were done, the results were compared. This was then repeated but with a disction within the data, this was "resampling" using random oversampling and to make it a 50-50 split of heallhy and high risks loans. Finally accuracy scores and classfication reports were used to go more in depth on the results of the models.


## Results

First Model with original data:
       
                  precision  recall  f1-score   support

           0       1.00      0.99      1.00     18765
           1       0.85      0.91      0.88       619

    accuracy                           0.99     19384
   macro avg       0.92      0.95      0.94     19384
weighted avg       0.99      0.99      0.99     19384

Second Model with Resampled data

                 precision   recall  f1-score   support

           0       1.00      0.99      1.00     18765
           1       0.84      0.99      0.91       619

    accuracy                           0.99     19384
   macro avg       0.92      0.99      0.95     19384
weighted avg       0.99      0.99      0.99     19384


## Summary

First Model:

The model does incredibly well predicting the "0"/ healthy loan with a 100% precision and a 99% recall. The model does decently well at predicting the "1"/ high-risk loan with a 85% precision and a 91% recall. Overall the model's accuracy score of 95% is really good but its not 100% meaning there's always things to keep an eye on since its not perfect.

Second Model:

The model does incredibly well at prediciton the the "0" healthy loan label with a precision of 100% and a recal of 99%. When it comes to the "1" high-risk loans, the logistic regression model doesnt perform as well when compared to the previous label, it has a precision of 84% (FPs), but it keeps the 99% recall. The model overall si great with a 99% accuaracy score but when you look in depth with the classification report results, it supports the line of thinking that unless the models has a 100%, you can never truly beleive is perfect.


Both Models performed well, both have really high accuracy scores but the devil lies within the details. The models need to be predict botht the "0" and the "1" as perfrectly as possible so the company doesnt miss a healthy loan opportunty or goes for a high risk loan opportunity. Additionally we do not want these two binary outcomes to be misslabeled as the wrong one. For this reason, the second model that contains the resampled data is the better choice, while the precision is 84% vs 85% of the first model, thge recall is 99% vs 91%, meaning that ratio of correctly predicted positive observations to the all observations in the loan status was much higher.