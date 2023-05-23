## Stacking
![image](https://github.com/fatihilhan42/Data_Science_Journey/assets/63750425/277e49dc-966b-4efb-9e1e-cc5856249f8d)

Stacking is an ensemble learning technique that involves training a model to combine the predictions of several base models. It is a meta-algorithm that builds a new model by learning how to combine the predictions of other models. In other words, it combines multiple models with different strengths and weaknesses to produce a better overall prediction.

Stacking is also known as stacked generalization or meta-ensembling. It was first introduced by Wolpert in 1992.

### How Stacking Works
The basic idea behind stacking is to train several base models on the training data and then use the predictions of these models as input features for a higher-level model called the meta-model. The meta-model then learns how to combine the predictions of the base models to produce the final prediction.

Here are the steps involved in stacking:

1. Split the training data into two parts: the first part is used to train the base models, and the second part is used to train the meta-model.
2. Train several base models on the first part of the training data.
3. Use the base models to make predictions on the second part of the training data.
4. Use the predictions of the base models as input features to train the meta-model on the second part of the training data.
5. Use the trained meta-model to make predictions on the test data.

### Advantages of Stacking

- Stacking can improve the accuracy of a model by combining the predictions of several base models.
- Stacking can help to overcome the limitations of individual models by using their strengths and compensating for their weaknesses.
- Stacking can be used with any type of model, whether it is a linear model, a tree-based model, or a neural network.

### Disadvantages of Stacking

- Stacking can be computationally expensive, as it involves training multiple models.
- Stacking can be sensitive to overfitting, especially if the base models are highly correlated.

### Example Implementation in Python

### Implementation of Stacking
Implementing stacking in Python can be done using various libraries, such as Scikit-learn. Here is an example of how to implement stacking using Scikit-learn:

```python
from sklearn.linear_model import LogisticRegression
from sklearn.naive_bayes import GaussianNB
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
from sklearn.datasets import load_breast_cancer
from mlxtend.classifier import StackingClassifier

# Load dataset
X, y = load_breast_cancer(return_X_y=True)

# Split into train and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# Initialize base models
lr = LogisticRegression(random_state=42)
nb = GaussianNB()
rf = RandomForestClassifier(random_state=42)

# Initialize meta model
meta = LogisticRegression(random_state=42)

# Initialize stacking classifier
sclf = StackingClassifier(classifiers=[lr, nb, rf], meta_classifier=meta)

# Train base models
lr.fit(X_train, y_train)
nb.fit(X_train, y_train)
rf.fit(X_train, y_train)

# Train stacking classifier
sclf.fit(X_train, y_train)

# Predict using base models
lr_pred = lr.predict(X_test)
nb_pred = nb.predict(X_test)
rf_pred = rf.predict(X_test)

# Predict using stacking classifier
sclf_pred = sclf.predict(X_test)

# Evaluate base models
lr_acc = accuracy_score(y_test, lr_pred)
nb_acc = accuracy_score(y_test, nb_pred)
rf_acc = accuracy_score(y_test, rf_pred)

# Evaluate stacking classifier
sclf_acc = accuracy_score(y_test, sclf_pred)

print("Logistic Regression accuracy: {:.2f}%".format(lr_acc * 100))
print("Naive Bayes accuracy: {:.2f}%".format(nb_acc * 100))
print("Random Forest accuracy: {:.2f}%".format(rf_acc * 100))
print("Stacking Classifier accuracy: {:.2f}%".format(sclf_acc * 100))


```
**
Logistic Regression accuracy: 97.08%
Naive Bayes accuracy: 94.15%
Random Forest accuracy: 97.08%
Stacking Classifier accuracy: 97.08%**

In this example, we use the Breast Cancer Wisconsin dataset, which contains information about breast cancer tumors and whether they are benign or malignant. We split the data into training and testing sets and then initialize three base models: logistic regression, Gaussian Naive Bayes, and random forest. We also initialize a meta model, which is used to combine the predictions of the base models.

We then create a **StackingClassifier** object, which takes the base models and meta model as parameters. We train the base models and the stacking classifier, and then make predictions using both the base models and the stacking classifier. We evaluate the performance of each model using accuracy score.

### Conclusion
Ensemble methods are powerful techniques for improving the performance of machine learning models. Stacking is a popular ensemble method that combines the predictions of multiple models to achieve higher accuracy than any single model alone. By using stacking, we can leverage the strengths of different models and mitigate their weaknesses, resulting in more robust and accurate predictions.
