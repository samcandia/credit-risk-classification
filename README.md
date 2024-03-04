# Background 

In this Challenge, I used various techniques to train and evaluate a model based on loan risk. I used a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

## Steps Taken 
##### Split the Data into Training and Testing Sets

* Read the lending_data.csv data from the Resources folder into a Pandas DataFrame.

* Created the labels set (y) from the “loan_status” column, and then create the features (X) DataFrame from the remaining columns.

* Split the data into training and testing datasets by using train_test_split.

##### Created a Logistic Regression Model with the Original Data

* Fit a logistic regression model by using the training data (X_train and y_train).

* Saved the predictions for the testing data labels by using the testing feature data (X_test) and the fitted model.

* Evaluated the model’s performance by Generating a confusion matrix and printing the classification report, 

##### Wrote a Credit Risk Analysis Report
* Found below.

# Original data Findings
 
##### Balanced Accuracy Report: 96.80%

##### Confusion Matrix: 

  18655        110

  36           583

##### Classification Report:


<img width="305" alt="image" src="https://github.com/samcandia/credit-risk-classification/assets/145384304/93098333-66e6-4dba-8d21-1ec9f6e0e575">


#### For class 0 (healthy loans):

* Precision: 1.00, meaning when the model predicts a loan as healthy, it is correct 100% of the time.
* Recall: 0.99, indicating that the model correctly identifies 99% of all healthy loans.
* F1-score: 1.00, a high value indicating a good balance between precision and recall.
* Support: 18765, the number of actual occurrences of healthy loans.

#### For class 1 (high-risk loans):

* Precision: 0.85, meaning when the model predicts a loan as high-risk, it is correct 85% of the time.
* Recall: 0.91, indicating that the model correctly identifies 91% of all high-risk loans.
* F1-score: 0.88, a lower value compared to class 0, indicating a slightly lower balance between precision and recall.
* Support: 619, the number of actual occurrences of high-risk loans.

 #### Taking into account both, the balanced accuracy report and the generalized classification report, the model predicts quite well. A balanced accuracy report of 95% suggests that the model does well classifying both classes while taking into account the imbalanced distribution.

#### The classification report suggests that the model correctly predicts healthy loans [0] 100% of the time and correctly predicts high-risk loans [1] 85% of the time from what it identifies.

# Findings with Resampled Data 
##### Balanced Accuracy Report: 99.36%

##### Confusion Matrix: 

  18647        118

  4           615

##### Classification Report:

<img width="301" alt="image" src="https://github.com/samcandia/credit-risk-classification/assets/145384304/1e0b3c8c-4e7f-4608-82ab-8b6909883583">

# Summary 

After applying the RandomOverSampler technique, we observe improvements in several metrics:

1. **Balanced Accuracy:** The balanced accuracy increased from 96.80% to 99.36%, indicating better overall performance in correctly classifying both classes while considering their imbalance.

2. **Confusion Matrix:** The number of false positives and false negatives decreased after oversampling, resulting in a more balanced distribution of predictions.

3. **Precision, Recall, and F1-score:** While precision remains relatively stable, recall and F1-score for the minority class (class 1) have improved. This indicates better performance in correctly identifying high-risk loans.

4. **Accuracy:** The overall accuracy remains the same (99%), suggesting that oversampling did not significantly impact the model's ability to classify instances correctly.

**Conclusion:**

Based on the provided evaluation metrics, the model after applying the RandomOverSampler technique appears to be better suited for the task at hand. It demonstrates improved performance in correctly identifying high-risk loans while maintaining high overall accuracy.

