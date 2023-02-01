# Multiple Linear Regression

Multiple linear regression is a type of linear regression that allows you to model the relationship between multiple independent variables and a single dependent variable. It is used when you have one continuous dependent variable and two or more independent variables.

The equation for multiple linear regression is:

$ y = b_0 + b_1x_1 + b_2x_2 + ... + b_nx_n $

where y is the dependent variable, $x_1, x_2, ..., x_n$ are the independent variables, and $b_0, b_1, b_2, ..., b_n$ are the coefficients.

To perform multiple linear regression using scikit-learn, you can use the LinearRegression class from the linear_model module. The process is similar to simple linear regression, with the main difference being that you will need to pass a 2D array of independent variables instead of a 1D array.



```Python
from sklearn.linear_model import LinearRegression

# create a LinearRegression object
reg = LinearRegression()

# fit the model to the data
reg.fit(X, y)

# make predictions
y_pred = reg.predict(X_test)

```

It is also important to note that in multiple linear regression, it is possible for some of the independent variables to be highly correlated with each other. This can lead to a phenomenon called multicollinearity, which can make it difficult to interpret the coefficients of the independent variables. To address this issue, you can use techniques such as principal component analysis (PCA) or regularization methods such as Ridge or Lasso.

Once you have fit your model, you can also evaluate its performance using metrics such as R-squared, mean squared error (MSE), or the coefficient of determination.

```Python
from sklearn.metrics import r2_score, mean_squared_error

# calculate R-squared
r2 = r2_score(y_test, y_pred)
print("R-squared: ", r2)

# calculate MSE
mse = mean_squared_error(y_test, y_pred)
print("Mean Squared Error: ", mse)
```

R-squared:  0.583299806221776
Mean Squared Error:  0.5460476751617075


It's also good to visualize the data and the fitted model to gain insights and understand the trends.
```Python
import matplotlib.pyplot as plt

plt.scatter(X, y)
plt.plot(X, reg.predict(X))
```

It is also important to note that in multiple linear regression, it is possible for some of the independent variables to be highly correlated with each other. This can lead to a phenomenon called multicollinearity, which can make it difficult to interpret the coefficients of the independent variables. To address this issue, you can use techniques such as principal component analysis (PCA) or regularization methods such as Ridge or Lasso.

It's also important to check assumptions of the model, such as normality of the errors, linearity, independence of errors, and homoscedasticity. If these assumptions are not met, it can affect the validity of the model's results.

