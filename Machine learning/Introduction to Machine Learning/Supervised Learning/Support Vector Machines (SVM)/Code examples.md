## Code Examples

```python 
from sklearn.datasets import make_classification
from sklearn.svm import SVC
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

# Generate a random dataset for binary classification
X, y = make_classification(n_samples=1000, n_features=10, n_informative=5, n_redundant=0, random_state=42)

# Split the dataset into training and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create an SVM classifier with a linear kernel
clf = SVC(kernel='linear')

# Train the classifier on the training data
clf.fit(X_train, y_train)

# Make predictions on the test data
y_pred = clf.predict(X_test)

# Evaluate the performance of the classifier
accuracy = accuracy_score(y_test, y_pred)
print(f"Accuracy: {accuracy:.3f}")
```
**Accuracy: 0.780**

In this example, we first generate a random binary classification dataset using make_classification function from scikit-learn. We then split the dataset into training and test sets using train_test_split. We create an SVM classifier with a linear kernel using SVC function, and train the classifier on the training data using the fit method. Finally, we make predictions on the test data using the predict method and evaluate the performance of the classifier using the accuracy score from accuracy_score function.

```python 
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.svm import SVC

# Load the iris dataset
iris = load_iris()

# Split the data into training and test sets
X_train, X_test, y_train, y_test = train_test_split(iris.data, iris.target, test_size=0.2, random_state=42)

# Create an SVM classifier
clf = SVC(kernel='linear')

# Fit the model to the training data
clf.fit(X_train, y_train)

# Make predictions on the test set
y_pred = clf.predict(X_test)

# Evaluate the performance of the model
score = clf.score(X_test, y_test)
print("Accuracy:", score)
```
**Accuracy: 1.0**

In this example, we're loading the iris dataset, splitting it into training and test sets, creating an SVM classifier with a linear kernel, fitting the model to the training data, making predictions on the test set, and evaluating the performance of the model using accuracy as the metric.

### A more complex example of using SVMs for multiclass classification with a real-world dataset.

```python 
from sklearn import datasets
from sklearn.model_selection import train_test_split
from sklearn.svm import SVC
from sklearn.metrics import accuracy_score

# Load the iris dataset
iris = datasets.load_iris()

# Split the dataset into training and test sets
X_train, X_test, y_train, y_test = train_test_split(iris.data, iris.target, test_size=0.2, random_state=42)

# Train an SVM model
svm = SVC(kernel='rbf', gamma='scale')
svm.fit(X_train, y_train)

# Predict on the test set and compute accuracy
y_pred = svm.predict(X_test)
accuracy = accuracy_score(y_test, y_pred)

print(f"Accuracy: {accuracy:.3f}")
```
**Accuracy: 1.000**

In this example, we load the iris dataset and split it into training and test sets. We then train an SVM model with an RBF kernel using the training data, and predict the target variable on the test set. Finally, we compute the accuracy of the model by comparing the predicted target variable with the true target variable on the test set. The iris dataset is a classic dataset for multiclass classification, as it contains three classes of flowers.

### An example of how to use the GridSearchCV class to tune hyperparameters for an SVM.

```python 
from sklearn.datasets import load_iris
from sklearn.model_selection import GridSearchCV, train_test_split
from sklearn.svm import SVC

# Load the iris dataset
iris = load_iris()
X, y = iris.data, iris.target

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Define the parameter grid to search over
param_grid = {'C': [0.1, 1, 10], 'kernel': ['linear', 'rbf', 'poly'], 'gamma': ['scale', 'auto']}

# Create an SVM object
svc = SVC()

# Create a GridSearchCV object
grid = GridSearchCV(svc, param_grid, cv=5)

# Fit the GridSearchCV object to the training data
grid.fit(X_train, y_train)

# Print the best hyperparameters found
print(f"Best hyperparameters: {grid.best_params_}")

# Make predictions on the test set using the best model
y_pred = grid.predict(X_test)

# Evaluate the performance of the model
score = grid.score(X_test, y_test)
print("Accuracy:", score)
```

**Best hyperparameters: {'C': 1, 'gamma': 'scale', 'kernel': 'linear'}
Accuracy: 1.0**