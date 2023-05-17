## Evaluation Metrics for Convolutional Neural Networks (CNNs)
![image](https://github.com/fatihilhan42/Data_Science_Journey/assets/63750425/43911fb7-d361-414b-aec6-d176a463af2e)

When training a CNN, it is important to have a way to evaluate the performance of the model. This is typically done by computing one or more evaluation metrics on a set of test data that is separate from the training data. There are several commonly used evaluation metrics for CNNs, each of which provides a different perspective on the performance of the model.

### Accuracy
Accuracy is perhaps the most commonly used evaluation metric for classification problems, including those tackled by CNNs. It simply measures the proportion of test examples that are classified correctly by the model. Formally, accuracy is defined as:

```python 
accuracy = (number of correctly classified examples) / (total number of examples)
```

Accuracy can be misleading in certain situations, however. For example, if the dataset is imbalanced (i.e., some classes have many more examples than others), a model that simply predicts the most common class for every example can achieve a high accuracy even though it is not actually learning anything meaningful. To overcome this issue, other evaluation metrics such as precision, recall, and F1 score can be used.

### Precision and Recall
Precision and recall are evaluation metrics that are commonly used in information retrieval and classification tasks. They are defined as:

```python 

precision = (number of true positives) / (number of true positives + number of false positives)
recall = (number of true positives) / (number of true positives + number of false negatives)

```

Here, a "true positive" is an example that is correctly classified as positive (i.e., as belonging to the class of interest), a "false positive" is an example that is incorrectly classified as positive, and a "false negative" is an example that is incorrectly classified as negative (i.e., as not belonging to the class of interest).

Precision measures the proportion of predicted positives that are actually positive, while recall measures the proportion of actual positives that are correctly identified. In general, higher precision means that the model is less likely to make false positive predictions, while higher recall means that the model is less likely to miss true positive predictions.

### F1 Score
The F1 score is a single evaluation metric that balances precision and recall. It is defined as the harmonic mean of precision and recall:

```python 
F1 = 2 * (precision * recall) / (precision + recall)
```

The F1 score ranges from 0 to 1, with higher values indicating better performance. Like precision and recall, the F1 score is affected by the trade-off between false positives and false negatives.

### Confusion Matrix
A confusion matrix is a table that summarizes the number of correct and incorrect predictions made by a classification model on a set of test data. It is often used to gain insight into the types of errors that a model is making, and to identify classes that are particularly challenging for the model. The confusion matrix is typically organized as follows:

| | Predicted Positive  | Predicted Negative |
| ------------- | ------------- | ------------ | 
| True Positive | TP  | FN  |
| True Negative | FP  | TN  |
                

                                    
Here, TP, FP, TN, and FN represent the number of true positives, false positives, true negatives, and false negatives, respectively.

### Receiver Operating Characteristic (ROC) curve
![image](https://github.com/fatihilhan42/Data_Science_Journey/assets/63750425/f2e32967-9ff2-4a35-a4a5-d73dab1fb45c)

The ROC curve is a plot of the true positive rate (TPR) against the false positive rate (FPR) for different classification thresholds. It is a useful tool for visualizing the performance of a binary classifier at different thresholds. The area under the ROC curve (AUC-ROC) is a common metric for evaluating the overall performance of a binary classifier, with values closer to 1 indicating better performance.

### Precision-Recall (PR) curve
The precision-recall curve is another tool for evaluating binary classifiers, particularly in cases where the positive class is rare. It is a plot of precision against recall for different classification thresholds. Precision is the proportion of true positives among all predicted positives, while recall is the proportion of true positives among all actual positives. The area under the PR curve (AUC-PR) is a common metric for evaluating the overall performance of a binary classifier on imbalanced datasets.

### Mean Average Precision (mAP)
mAP is a commonly used metric for evaluating object detection models. It is calculated as the mean of the average precisions for each class, where the average precision for a class is the area under the precision-recall curve for that class. mAP takes into account both the precision and recall of the model across multiple thresholds and is useful for evaluating the overall performance of an object detection model across multiple object categories.

### Intersection over Union (IoU)
IoU is a metric commonly used in object detection tasks to measure the similarity between the predicted bounding box and the ground truth bounding box. It is calculated as the ratio of the intersection of the two bounding boxes to the union of the two bounding boxes. An IoU score of 1 indicates a perfect match between the predicted and ground truth bounding boxes, while scores closer to 0 indicate poor performance.

These are some of the common evaluation metrics used for CNNs in various tasks. It's important to choose appropriate metrics based on the specific task at hand, as different metrics may be more or less appropriate depending on the problem domain and the goals of the model.
