# credit-risk-classification

## Introduction

This case study aims to build a model to predict the risk of lending loans to clients. The model is based on data with many factors, including teh loan size, interest rate, debt, income, numer of accounts, and derogatory marks. The loan status was also included in the data, which was used as the target variable. `train_test_split` from SkikitLearn split the dataset into X and y testing and training data, with y being loan status, and X being all of the fea

**The Model**

The `LogisticRegression` classifier from SkikitLearn was used to learn from the training data. The logistic regression algorithm uses a sigmoid function to perform a binary classification of one or multiple inputs, or features (X). Based on the features, the algorithm predicts a single target variable, or label (y). It is a algorithm in which the results have high interpretability.

## Analysis

Confusion Matrix:

- True Negative: 18663
- True Positive: 563
- False Negative: 56
- False Positive: 102

Classification Report:

**Precision**
 - Healthy Loan: 1.00
 - High-Risk Loan: 0.85

- Accuracy
  - Macro Average: 0.92
  - Weighted Average: 0.99

**Recall**
 - Healthy Loan: 0.99
 - High-Risk Loan: 0.91

- Accuracy
  - Macro Average: 0.95
  - Weighted Average: 0.99

## Summary

On a high level, the model appears to deliver fairly accurate results.

There are a few things to note, however. While healty loans have a precision and recall of 1.00 and 0.99, high-risk loans have a precision and recall of only 0.85 and 0.91, respectively.

**Precision and False Positives**

The precision of 0.85 indicates that high-risk loans were over-predicted to some extent, creating false-positives. Typically, false-positives are not necessarily the worst outcome, since a client labeled as high-risk could be further examined to see if that is actually the case. In the finance industry, it is better to be cautious when issuing loans.

**Recall and False Negatives**

While the 56 false-negatives are not much when compared to the 18,663 true negatives, they do appear to be significant relative to the true positives. This is the cause of the recall of 0.91 for the high-risk loans. False-negatives would be more cause for concern, since a financial institution cannot afford lending to a high-risk client by mistake.

**Conclusion and Next Steps**

For next steps, I would look at some other algorithms for predicting this data. For classifiers, I typically resort to implementing a random forest, which is well-kown for its accuracy in predicting data, even when compared to single decision trees. The current model isn't bad, but a differnt algorithm could show improvements with the precision and recall for high-risk loans.