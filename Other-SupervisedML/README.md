# CONVERSION RATE CHALLENGE

## Project goals
**Create a model that predicts whether a given user will subscribe to the newsletter, using only a few pieces of information about the user.**

✅ Getting started with source data
src
|_conversion_data_train.csv : contains labelled data with columns country, age, new_user, source, total_pages_visited, converted 
|_conversion_data_test.csv : contains unlabelled data (without the converted column (target variable))
|_conversion_data_test_labels.csv : contains the converted column (target variable) need for the model evaluation after subbmission

✅ Make EDA
* Data description
* Some statistics
* Manage outliers
* Some visualizations
* Preprocessing

✅ Use template to have baseline model : Logistic Regression
* Use one columns for training 'total_pages_visited'
* Evaluate the model f1 score
* Make predictions on the test set
* Make submission to TA

✅ Improve the model
* Use more columns for training
* Evaluate the model f1 score
* Make predictions on the test set
* Make submission to TA

✅ Analyse the results, Interpret the coefficients
* Use the coefficients to interpret the model

✅ Recommandations