## Code Examples

```python 
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import accuracy_score

# Load the iris dataset
iris = load_iris()

# Split the data into training and test sets
X_train, X_test, y_train, y_test = train_test_split(
    iris.data, iris.target, test_size=0.2, random_state=42)

# Create a k-NN classifier
knn = KNeighborsClassifier(n_neighbors=3)

# Fit the model to the training data
knn.fit(X_train, y_train)

# Make predictions on the test data
y_pred = knn.predict(X_test)

# Calculate the accuracy of the model
accuracy = accuracy_score(y_test, y_pred)

# Print the accuracy of the model
print(f"Accuracy: {accuracy:.2f}")
```

**Accuracy: 1.00**

In this example, we load the Iris dataset and split it into training and test sets using scikit-learn's **train_test_split** function. We then create a **KNeighborsClassifier** object with **n_neighbors=3** and fit it to the training data using the **fit** method. We then make predictions on the test data using the **predict** method and calculate the accuracy of the model using the **accuracy_score** function from scikit-learn's **metrics** module. Finally, we print the accuracy of the model.


### Another example:

Here's an example of using k-NN on the Auto MPG dataset using the Pandas library and the data hosted on the UCI Machine Learning Repository:

```python 
import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsRegressor
from sklearn.metrics import mean_squared_error

# Load the Auto MPG dataset from UCI ML Repository
url = "https://archive.ics.uci.edu/ml/machine-learning-databases/auto-mpg/auto-mpg.data"
names = ['mpg', 'cylinders', 'displacement', 'horsepower', 'weight', 'acceleration', 'model_year', 'origin', 'car_name']
df = pd.read_csv(url, names=names, delim_whitespace=True)

# Drop the "car_name" column since it's irrelevant for regression
df.drop('car_name', axis=1, inplace=True)

# Replace missing values with NaN
df.replace('?', np.nan, inplace=True)

# Convert horsepower column to numeric type
df['horsepower'] = pd.to_numeric(df['horsepower'])

# Drop any rows with NaN values
df.dropna(inplace=True)

# Split the data into training and test sets
X_train, X_test, y_train, y_test = train_test_split(df.drop('mpg', axis=1), df['mpg'], test_size=0.2, random_state=42)

# Create a k-NN regression model
knn = KNeighborsRegressor()

# Fit the model to the training data
knn.fit(X_train, y_train)

# Evaluate the model on the test data
y_pred = knn.predict(X_test)
mse = mean_squared_error(y_test, y_pred)
print(f"Test MSE: {mse:.3f}")
```

**Test MSE: 17.753**

Note that this example uses the KNeighborsRegressor class instead of the KNeighborsClassifier class, since the Auto MPG dataset is a regression problem rather than a classification problem. 
