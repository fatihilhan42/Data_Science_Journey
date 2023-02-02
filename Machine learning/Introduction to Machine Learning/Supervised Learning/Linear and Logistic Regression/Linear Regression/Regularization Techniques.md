Regularization techniques are methods used to prevent overfitting in a model by adding a penalty term to the loss function. There are two main types of regularization techniques: L1 regularization and L2 regularization.

L1 regularization, also known as Lasso regularization, adds a penalty term to the loss function that is proportional to the absolute value of the coefficients. This results in some coefficients being set to zero, effectively removing them from the model.

L2 regularization, also known as Ridge regularization, adds a penalty term to the loss function that is proportional to the square of the coefficients. This results in smaller, non-zero coefficients.

Both L1 and L2 regularization can be added to linear and logistic regression models in scikit-learn by setting the "penalty" parameter to "l1" or "l2" respectively, and setting the "alpha" parameter to a non-zero value.

It should be noted that using too much regularization can lead to underfitting, so it's important to find the right balance between preventing overfitting and keeping enough information in the model. Additionally, using cross-validation to evaluate model performance can help to find the optimal regularization strength.

Example usage of L1 regularization in scikit-learn:


```Python

from sklearn.linear_model import Lasso
reg = Lasso(alpha=0.1)
reg.fit(X, y)

```


Example usage of L2 regularization in scikit-learn:

```Python
from sklearn.linear_model import Ridge
reg = Ridge(alpha=0.1)
reg.fit(X, y)
```

It is also possible to use Elastic Net regularization which is a combination of L1 and L2 regularization, this can be used by setting the "penalty" parameter to "elasticnet" and tuning the l1_ratio parameter to balance the amount of L1 and L2 regularization.
```Python
from sklearn.linear_model import ElasticNet
reg = ElasticNet(alpha=0.1, l1_ratio=0.5)
reg.fit(X, y)
```

Regularization technique can be used to prevent overfitting, it will be efficient to use it in cases where the dataset is large or has many features. It is also a good idea to use cross-validation to find the optimal regularization strength.