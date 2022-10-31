# Credit_Risk_Analysis

## Objective
The purpose of this analysis is to select an algorithm that can best predict HIGH or LOW credit risk by training using historical credit information. This is done by using a number of resampling models and algorithms to find a configuration with the best fit based on their accuracy and precision scores.

## Background
Multiple methods were used, some resampling the data to provide an even analysis for low and high risk borrowers with Logistic Regression (there were far fewer "high risk" borrowers identified in the dataset than "low risk"). Other methods utilized 'ensemble' imbalanced learning modules. All of these were compared to determine what the best method may be for predicting credit risk in the data.

## Summary and Analysis of Results
### resampling technique

Oversampling, both naive and with SMOTE, did not yield a useable model for the prediction of bad loans. Naive oversampling resulted in a precision score of 0.01 and recall of 0.70. The F1 score of 0.02 reflected athe low precision score. SMOTE oversampling similarly resulted in a precision score of 0.01 and recall of 0.63, and a F1 score of 0.02.

A model with undersampling yielded similarly poor results, with a precision score of 0.01, recall of 0.65, and F1 score of 0.01.

Combination sampling resulted in a precision score of 0.01 and recall of 0.69, and a F1 score of 0.01. While the recall score is marginally better than that of the other models, the overall performance of the model is still poor.

These models are inadequately predictive, and are not recommended for commercial application.

### ensemble
The random forest classifier, with and without AdaBoost, failed to achieve useable performance. The balanced random forest classifier's precision is 0.03, meaning that in 100 loan applications that were flagged to be bad, only 4 were actually bad loan applications. The model's recall/sensitivity is 0.70, meaning that it detected 67% of bad loan applications. The F1 score is low at 0.06, since either a low precision or recall will result in a lower F1 score.

The random forest classifier with AdaBoost, while achieving better results, still suffered from inadequate predictive power. Its precision score is 0.09 and its recall 0.92. The F1 score, again, is skewed low at 0.16 by the low precision score.

The performances of both models are insufficient for commercial application. 

## Conclusion and Recommendations
The above indicates that each method saw very high precision for predicting low risk borrowers, while seeing extrememly low precision predicting high risk borrowers. Recall scores using resampling within the Logistic Regression model were highest on average for Random Oversampling and SMOTE. Individual scores were highest for Low Risk using SMOTE, and High Risk using SMOTEENN. Balanced accuracy among the resampling methods was highest for Random Oversampling.

The ensemble methods saw recall scores on average to be highest for the Easy Ensemble Classifier, but individually the Balanced Random Forest Classifier saw the highest value for Low Risk and Easy Ensemble Classifier for High Risk. Balanced accuracy among the ensemble methods was highest for the Easy Ensemble Classifier.

Given that the dataset is imbalanced, the recall and balanced accuracy scores are the better metrics to follow. Given this, the best performing model for the data was the Easy Ensemble Classifier method. Further exploration should be done, removing columns that do not perform well (if at all) given the importance scores.