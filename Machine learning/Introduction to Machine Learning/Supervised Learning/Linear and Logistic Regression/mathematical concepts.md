# Linear Regression
Linear regression is a technique for modeling the relationship between a dependent variable (target variable) and one or more independent variables (features). The goal is to find the line of best fit that minimizes the difference between the predicted values and the actual values.

The equation for a simple linear regression model is given by:

y = beta0 + beta1 * x

where y is the target variable, x is the independent variable, and $\beta_0$ and $\beta_1$ are the coefficients of the model. The coefficients represent the slope and y-intercept of the line of best fit. The goal is to find the values of $\beta_0$ and $\beta_1$ that minimize the difference between the predicted values and the actual values, this is done by using optimization algorithm such as gradient descent or normal equation.

where y is the target variable, x is the independent variable, and $\beta_0$ and $\beta_1$ are the coefficients of the model. The coefficients represent the slope and y-intercept of the line of best fit. The goal is to find the values of $\beta_0$ and $\beta_1$ that minimize the difference between the predicted values and the actual values, this is done by using optimization algorithm such as gradient descent or normal equation.

# Logistic Regression
Logistic regression is a technique for modeling the relationship between a dependent variable (target variable) and one or more independent variables (features). Logistic regression is used for predicting a binary target variable, where the goal is to estimate the probability of the target variable being one of two possible values (e.g. 1 or 0, yes or no, true or false).

The equation for a simple logistic regression model is given by:

p = 1 / (1 + e^(-(beta0 + beta1 * x)))

 
where p is the probability of the target variable being 1, x is the independent variable, and $\beta_0$ and $\beta_1$ are the coefficients of the model. The coefficients represent the slope and y-intercept of the line of best fit. The goal is to find the values of $\beta_0$ and $\beta_1$ that maximize the likelihood of the observed data.

```Python
# Importing libraries
from sklearn.linear_model import LinearRegression

# Creating the Linear Regression Model
lin_reg = LinearRegression()

# Fitting the Model
lin_reg.fit(X_train, y_train)

# Making Predictions
y_pred = lin_reg.predict(X_test)

# Evaluating the Model
from sklearn.metrics import mean_squared_error
print('RMSE:', np.sqrt(mean_squared_error(y_test, y_pred)))
```
```Python
import matplotlib.pyplot as plt

# Creating the scatter plot
plt.scatter(X, y)

# Plotting the line of best fit
plt.plot(X, lin_reg.predict(X), color='red')

plt.show()
```


