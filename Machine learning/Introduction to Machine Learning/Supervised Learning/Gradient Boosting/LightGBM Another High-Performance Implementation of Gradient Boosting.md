## LightGBM: Another High-Performance Implementation of Gradient Boosting
![image](https://github.com/fatihilhan42/Data_Science_Journey/assets/63750425/61bc9da0-8dab-4bee-8936-8b462b717348)

LightGBM is an open-source implementation of gradient boosting that was developed by Microsoft. It is designed to be highly efficient and scalable, making it well-suited for large datasets.

### Features
Some of the key features of LightGBM include:

- **Gradient-based One-Side Sampling (GOSS):** This is a sampling strategy that is used to speed up the training process by focusing on the most important data points. GOSS works by prioritizing the samples with larger gradients, which are typically the most informative.
- **Exclusive Feature Bundling (EFB):** This is a feature engineering technique that is used to group together related features. By doing this, the algorithm can more easily capture complex interactions between features.
- **Histogram-based Gradient Boosting:** LightGBM uses a histogram-based approach to split continuous features into discrete bins. This helps to reduce memory usage and improves the speed of the algorithm.

### Usage
LightGBM can be used with a variety of programming languages, including Python, R, and C++. Here's an example of how to use LightGBM in Python:

```python 
import lightgbm as lgb
import numpy as np
import pandas as pd
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split

# Load the data
data = load_iris()
X, y = data.data, data.target

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create a LightGBM dataset
train_data = lgb.Dataset(X_train, label=y_train)

# Set the hyperparameters
params = {
    'objective': 'multiclass',
    'num_class': 3,
    'metric': 'multi_logloss'
}

# Train the model
model = lgb.train(params, train_data, num_boost_round=100)

# Make predictions on the testing set
y_pred = model.predict(X_test)

# Print the accuracy score
print('Accuracy:', np.mean(np.argmax(y_pred, axis=1) == y_test))
```
Output ---> **Accuracy: 1.0**

In this example, we first load the Iris dataset and split it into training and testing sets. We then create a LightGBM dataset using the lgb.Dataset function. Next, we set the hyperparameters for the model and train it using the lgb.train function. Finally, we make predictions on the testing set and print the accuracy score.

Conclusion
LightGBM is a powerful implementation of gradient boosting that offers several features to improve the speed and accuracy of the algorithm. Its use of GOSS and EFB make it particularly well-suited for large datasets with high-dimensional features.
