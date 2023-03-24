# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
The purpose of this analysis was to compare the same machine learning model with "different" data sets, the original and one resampled. The original dataset is heavily skewed towards not risk loans which could then skew the model to predict that a loan is not at risk, defeating the purpose. The hopes is that by having an equal amount of data in both the classification groups using the resample method, the model can better learn features of at risk loans.

* Explain what financial information the data was on, and what you needed to predict.
The goal was to predict whether or not a loan would be at risk based off the following features: loan size, interest rate, borrower income, debt to income ratio, number of accounts, derogatory remarks and total debt. 

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
The original dataset had a majority class of not-at-risk loans, with 75036 examples, compared to only 2500 examples of at-risk loans. 

* Describe the stages of the machine learning process you went through as part of this analysis.
1 Spliting the data into the X and y variables--or the features and the targets.

2 Further splitting X and y into training and testing sets. 

3 (Model 1) Instantiate and fitting the LogsticRegression model
  (Model 2) Instantiating and fitting the RandomOversampler to the x and y training set to add examples to the minority class.

4 (Model 1) Making predictions
  (Model 2) Instantiating and fitting the LogisticRegression Model 

5 (Model 2) Making predictions 

* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).
Logistic Regression- 

Resampling- balances a dataset that has a drastic difference between classes, so the model can better learn the features of the minority class
## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
-95% of the time, the model will have accurate results. 
-It will identify 99% of non-risk loans, guessing correctly every time (100%) of that 99%
-It will only identify 91% of at-risk loans though, guessing correctly only 85% of the time.

* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
-99% of the time, the model will have accurate results. 
-It also identifies 99% of non-risk loans, with 100% precision. 
-It identifies 99% of at risk-loans with 84% precision. 


## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )
If you do not recommend any of the models, please justify your reasoning.

For this problem, accurately identifying an at risk loan (1) is more important.

Both models do well to predict not-at risk loans, identifying 99% of good loans with 100% precision, but the first model is not as good at identifying at risk loans, only identifying 91% with a precision of 85%. The resampled model performs better of the two in regards to identifying at risk loans, correctly predicting them 99% of the time, but it only has a precision of 84%. 

However, I would caution on using either. Both models have a decent amount of false positives which could lead to defaults and the first one has a decent amount of false negatives which could just lead to angry would-have-been customers. If one had to be put into production, now, I'd recommend the first, given it's lower count of false positives and I would also institute the caveat that all negatives need to be reviewed before final decision. However, my overall recommendation would be to continue to tweak the model by either pulling in more features or gathering more data to train on. 



