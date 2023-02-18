# Fitting and Evaluating Random Forest

Random forest is an ensemble learning method that combines multiple decision trees to create a more accurate and stable model. It works by building a multitude of decision trees at training time and outputting the class that is the mode of the classes (classification) or mean prediction (regression) of the individual trees.

The **RandomForestClassifier** class in scikit-learn is used to implement random forest for classification problems, while the **RandomForestRegressor** class is used for regression problems. The process of fitting and evaluating a random forest model is similar to decision trees. Here's an example code:

```python
from sklearn.ensemble import RandomForestClassifier
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

# Load the iris dataset
iris = load_iris()
X = iris.data
y = iris.target

# Split the data into training and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=0)

# Train the random forest classifier with 100 trees
clf = RandomForestClassifier(n_estimators=100, random_state=0)
clf.fit(X_train, y_train)

# Predict the test data and evaluate the accuracy
y_pred = clf.predict(X_test)
accuracy = accuracy_score(y_test, y_pred)
print(f"Accuracy: {accuracy}")

```
**Accuracy: 0.9777777777777777**


In this code, we load the iris dataset and split it into training and test sets. We then train the **RandomForestClassifier**with 100 trees and predict the test data. Finally, we evaluate the accuracy of the model using the **accuracy_score** function from scikit-learn's **metrics** module.

The **RandomForestClassifier** class has many hyperparameters that can be tuned to improve the performance of the model. Some of the important hyperparameters include **n_estimators**, which specifies the number of trees to be used in the forest, and **max_depth**, which limits the maximum depth of each decision tree. Hyperparameter tuning can be done using techniques such as grid search or randomized search.

In addition to accuracy, other evaluation metrics such as precision, recall, and F1 score can be used to evaluate the performance of a random forest model. These metrics can be computed using the **classification_report** function from the **metrics** module.
