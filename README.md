# credit-risk-classification

## Introduction

This case study aims to build models to predict the risk of lending loans to clients. The models are based on data with many factors, including the loan size, interest rate, debt, income, numer of accounts, and derogatory marks. The loan status was also included in the data, which was used as the target variable. `train_test_split` from SkikitLearn split the dataset into X and y testing and training data, with y being loan status, and X being all of the features.

**The Models**

The `LogisticRegression` classifier from ScikitLearn was used to learn from the training data. The logistic regression algorithm uses a sigmoid function to perform a binary classification of one or multiple inputs, or features (X). Based on the features, the algorithm predicts a single target variable, or label (y). It is a algorithm in which the results have high interpretability.

In addition, the `RandomForestClassifier` from ScikitLearn provided a second algorithm for the purposes of comparison. Unlike a logistic regression, random forest is an ensemble algorithm of many decision trees, each of them taking on different parts of the data. While logistic regression is known for its interpretability, random forest is known for its high accuracy when classifying data.

## Analysis

**Left: Logistic Regression, Right: Random Forest**

Confusion Matrix:

- True Negative: 18663, 18665
- True Positive: 563, 557
- False Negative: 56, 62
- False Positive: 102, 100

Classification Report:

**Precision**
 - Healthy Loan: 1.00, 1.00
 - High-Risk Loan: 0.85, 0.85

- Accuracy
  - Macro Average: 0.92, 0.92
  - Weighted Average: 0.99, 0.99

**Recall**
 - Healthy Loan: 0.99, 0.99
 - High-Risk Loan: 0.91, 0.90

- Accuracy
  - Macro Average: 0.95, 0.95
  - Weighted Average: 0.99, 0.99

## Summary

On a high level, the model appears to deliver fairly accurate results.

There are a few things to note, however. While healty loans have a precision and recall of 1.00 and 0.99, high-risk loans have a precision and recall of only 0.85 and 0.91, respectively.

**Precision and False Positives**

The precision of 0.85 indicates that high-risk loans were over-predicted to some extent, creating false-positives. Typically, false-positives are not necessarily the worst outcome, since a client labeled as high-risk could be further examined to see if that is actually the case. In the finance industry, it is better to be cautious when issuing loans.

**Recall and False Negatives**

While the 56 false-negatives are not much when compared to the 18,663 true negatives, they do appear to be significant relative to the true positives. This is the cause of the recall of 0.91 for the high-risk loans. False-negatives would be more cause for concern, since a financial institution cannot afford lending to a high-risk client by mistake.

**Comparing the Models**

At first glance, the performance between the models appears rather insignificant. However, when looking at the confusion matrix, the logistic regression model actually did slightly better at detecting true negatives. The random forest model had more difficulty with predicting true negatives, leading to some false negatives (leading to the 1% difference in recall between the two models).

**Conclusion and Next Steps**

Since the logistic regression performed better, I would actually stick to this model over the random forest. Because the metrics could still be improved, and a change in algorithm selection was ineffective, some next steps would include either fine-tuning the model, further examining the data, or both. Another idea would be to look at the false positives and false negatives and see how they are being passed over by the algorithms.