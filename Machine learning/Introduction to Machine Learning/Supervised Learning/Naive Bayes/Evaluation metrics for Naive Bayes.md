# Evaluation metrics for Naive Bayes
![image](https://github.com/fatihilhan42/Data_Science_Journey/assets/63750425/ad160a37-aa8a-4c30-ad98-1d2bf42204fa)

Naive Bayes is a probabilistic classification algorithm that can be used for a variety of tasks, including binary and multiclass classification, text classification, and spam filtering. When using Naive Bayes, it's important to evaluate the performance of the model using appropriate metrics to ensure that it's making accurate predictions.

Here are some common evaluation metrics used for Naive Bayes:

## Confusion matrix
A confusion matrix is a table that is often used to describe the performance of a classification model. It compares the predicted values to the actual values and shows the number of true positives, true negatives, false positives, and false negatives.


|                 | Predicted Positive  | Predicted Negative |
| --------------- | ------------- | ------------- | 
| Actual Positive | True Positive (TP)  | False Negative (FN)  |
| Actual Negative | 	False Positive (FP)  | True Negative (TN) |

- **True positive (TP):** The model correctly predicted the positive class.
- **False positive (FP):** The model incorrectly predicted the positive class.
- **True negative (TN):** The model correctly predicted the negative class.
- **False negative (FN):** The model incorrectly predicted the negative class.

## Accuracy
Accuracy measures the proportion of correct predictions out of the total number of predictions.

**accuracy = (TP + TN) / (TP + TN + FP + FN)**

## Precision
Precision measures the proportion of true positives among all positive predictions.

**precision = TP / (TP + FP)**

## Recall
Recall measures the proportion of true positives among all actual positive instances.

**recall = TP / (TP + FN)**

## F1 score
The F1 score is the harmonic mean of precision and recall, providing a single score that balances both metrics.

**F1 = 2 * (precision * recall) / (precision + recall)**

## Area under the ROC curve (AUC-ROC)
The ROC (receiver operating characteristic) curve is a plot of the true positive rate (recall) versus the false positive rate (1-specificity) for different classification thresholds. The AUC-ROC measures the area under this curve, which provides a single score that measures the overall performance of the model.

These evaluation metrics can be computed using various Python libraries such as scikit-learn and numpy. It's important to choose the appropriate evaluation metric based on the specific problem and the objectives of the model.

