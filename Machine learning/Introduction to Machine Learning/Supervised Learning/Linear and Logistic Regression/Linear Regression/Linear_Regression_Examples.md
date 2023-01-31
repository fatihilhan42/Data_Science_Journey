Here is an example of data loading and preprocessing for linear regression using the California residential dataset from scikit-learn:

```Python
from sklearn.datasets import fetch_california_housing
from sklearn.model_selection import train_test_split

housing = fetch_california_housing()
X = housing.data
y = housing.target

# Split the data into training and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```
Here is an example of fitting a linear regression model to the data using scikit-learn:

```Python
from sklearn.linear_model import LinearRegression

# Create an instance of the linear regression model
reg = LinearRegression()

# Fit the model to the training data
reg.fit(X_train, y_train)
```
And here is an example of evaluating the performance of the model using mean squared error and R-squared:

```Python
from sklearn.metrics import mean_squared_error, r2_score

# Make predictions on the test data
y_pred = reg.predict(X_test)

# Calculate the mean squared error and R-squared score
mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)

print("Mean Squared Error: ", mse)
print("R-Squared Score: ", r2)
```

Mean Squared Error:  0.5558915986952425
R-Squared Score:  0.5757877060324521

And as for visualizing the concepts, we can use matplotlib library and create scatter plot of the data, and line plot of the fitted model like this:

```Python
import matplotlib.pyplot as plt

# Plot the data
plt.scatter(X_train[:,0], y_train)

# Plot the fitted model
plt.plot(X_train[:,0], reg.predict(X_train), color='r')

plt.show()
```

2.resim 


```Python
from sklearn.linear_model import LinearRegression
from sklearn.datasets import make_regression

# Generate sample data
X, y = make_regression(n_samples=100, n_features=1, noise=20)

# Create and fit the model
reg = LinearRegression().fit(X, y)

# Print the model coefficients
print(reg.coef_)
print(reg.intercept_)

# Predict using the model
y_pred = reg.predict(X)

# Plot the data and the model predictions
import matplotlib.pyplot as plt

plt.scatter(X, y)
plt.plot(X, y_pred)
plt.show()
```

[61.90983722]
-1.7070695847965252 

1.Resim 

This code generates a sample dataset using the make_regression function from scikit-learn, which creates a linear dataset with a specified number of samples and features. Then, it creates a LinearRegression model, fits it to the data, and prints the model coefficients (slope and intercept). Finally, it uses the model to predict the output for the input data and plots the data points and the model predictions.

