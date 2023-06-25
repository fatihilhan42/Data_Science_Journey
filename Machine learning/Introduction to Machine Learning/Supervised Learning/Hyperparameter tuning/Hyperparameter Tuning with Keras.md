## Hyperparameter Tuning with Keras
Keras is a popular deep learning library in Python that provides a high-level interface for building and training neural networks. Hyperparameter tuning is a critical step in optimizing the performance of neural networks, and Keras offers several techniques to facilitate this process. In this guide, we will explore various methods available in Keras for hyperparameter tuning.

### Manual Hyperparameter Tuning
One of the simplest ways to perform hyperparameter tuning in Keras is through manual experimentation. This involves manually selecting different values for hyperparameters and training multiple models to evaluate their performance. The process typically involves adjusting hyperparameters such as learning rate, batch size, number of layers, number of neurons, and activation functions.

Here's an example of how to perform manual hyperparameter tuning in Keras:

```python
from keras.models import Sequential
from keras.layers import Dense, Dropout
from keras.optimizers import Adam
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split

# Load the Iris dataset
iris = load_iris()
X, y = iris.data, iris.target

# Split the dataset into training and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Define the hyperparameters
learning_rate = 0.001
batch_size = 32
num_epochs = 50

# Create a neural network model
model = Sequential()
model.add(Dense(64, activation='relu', input_dim=4))
model.add(Dense(64, activation='relu'))
model.add(Dense(3, activation='softmax'))

# Compile the model
model.compile(optimizer=Adam(learning_rate), loss='sparse_categorical_crossentropy', metrics=['accuracy'])

# Train the model
model.fit(X_train, y_train, batch_size=batch_size, epochs=num_epochs, verbose=1)

# Evaluate the model on the test set
loss, accuracy = model.evaluate(X_test, y_test, verbose=0)

```

In this example, we manually tune hyperparameters such as learning rate, batch size, and number of epochs. We define a neural network model with two hidden layers, ReLU activation, and a softmax output layer for multi-class classification. We compile the model with the Adam optimizer and sparse categorical cross-entropy loss. Finally, we train the model on the training data and evaluate its performance on the test set.

### Grid Search Hyperparameter Tuning
Grid Search is a systematic method for hyperparameter tuning that involves defining a grid of hyperparameter values and exhaustively searching all possible combinations. Keras provides integration with the Scikit-Learn library, allowing us to use the GridSearchCV class to perform Grid Search hyperparameter tuning.

Here's an example of how to perform Grid Search hyperparameter tuning in Keras:

```python
from keras.wrappers.scikit_learn import KerasClassifier
from sklearn.datasets import load_iris
from sklearn.model_selection import GridSearchCV, train_test_split
from keras.models import Sequential
from keras.layers import Dense
from keras.optimizers import Adam

# Load the Iris dataset
iris = load_iris()
X, y = iris.data, iris.target

# Split the dataset into training and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create a function to build the Keras model
def build_model(learning_rate=0.001, num_neurons=64):
    model = Sequential()
    model.add(Dense(num_neurons, activation='relu', input_dim=4))
    model.add(Dense(num_neurons, activation='relu'))
    model.add(Dense(3, activation='softmax'))
    model.compile(optimizer=Adam(learning_rate), loss='sparse_categorical_crossentropy', metrics=['accuracy'])
    return model

# Create a KerasClassifier wrapper
model = KerasClassifier(build_fn=build_model, verbose=0)

# Define the hyperparameters and their values
param_grid = {
    'learning_rate': [0.001, 0.01, 0.1],
    'num_neurons': [32, 64, 128]
}

# Perform Grid Search Cross-Validation
grid_search = GridSearchCV(estimator=model, param_grid=param_grid, cv=3)
grid_search.fit(X_train, y_train)

# Get the best hyperparameters and performance score
best_params = grid_search.best_params_
best_score = grid_search.best_score_

# Evaluate the model on the test set
best_model = grid_search.best_estimator_
loss, accuracy = best_model.evaluate(X_test, y_test, verbose=0)

```

In this example, we define a function build_model that creates a Keras model with two hidden layers and accepts hyperparameters learning_rate and num_neurons as arguments. We then wrap this function with the KerasClassifier class to make it compatible with Scikit-Learn. We define a grid of hyperparameter values using the param_grid dictionary. The GridSearchCV class performs the grid search cross-validation, iterating over all possible combinations of hyperparameters. We obtain the best hyperparameters and performance score from the best_params_ and best_score_ attributes, and evaluate the best model on the test set.

### Random Search Hyperparameter Tuning
Random Search is an alternative to Grid Search that samples hyperparameters from a specified distribution. Unlike Grid Search, which exhaustively searches all possible combinations, Random Search randomly selects a subset of hyperparameter combinations, making it more efficient for high-dimensional hyperparameter spaces. Keras provides integration with Scikit-Learn's RandomizedSearchCV class to perform Random Search hyperparameter tuning.

Here's an example of how to perform Random Search hyperparameter tuning in Keras:

```python
from keras.wrappers.scikit_learn import KerasClassifier
from sklearn.datasets import load_iris
from sklearn.model_selection import RandomizedSearchCV, train_test_split
from keras.models import Sequential
from keras.layers import Dense
from keras.optimizers import Adam
from scipy.stats import uniform, randint

# Load the Iris dataset
iris = load_iris()
X, y = iris.data, iris.target

# Split the dataset into training and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create a function to build the Keras model
def build_model(learning_rate=0.001, num_neurons=64):
    model = Sequential()
    model.add(Dense(num_neurons, activation='relu', input_dim=4))
    model.add(Dense(num_neurons, activation='relu'))
    model.add(Dense(3, activation='softmax'))
    model.compile(optimizer=Adam(learning_rate), loss='sparse_categorical_crossentropy', metrics=['accuracy'])
    return model

# Create a KerasClassifier wrapper
model = KerasClassifier(build_fn=build_model, verbose=0)

# Define the hyperparameters and their distributions
param_dist = {
    'learning_rate': uniform(0.001, 0.1),
    'num_neurons': randint(32, 128)
}

# Perform Randomized Search Cross-Validation
random_search = RandomizedSearchCV(estimator=model, param_distributions=param_dist, n_iter=10, cv=3)
random_search.fit(X_train, y_train)

# Get the best hyperparameters and performance score
best_params = random_search.best_params_
best_score = random_search.best_score_

# Evaluate the model on the test set
best_model = random_search.best_estimator_
loss, accuracy = best_model.evaluate(X_test, y_test, verbose=0)

```

In this example, we define a function build_model that creates a Keras model with two hidden layers and accepts hyperparameters learning_rate and num_neurons as arguments. We wrap this function with the KerasClassifier class to make it compatible with Scikit-Learn. We define a distribution of hyperparameters using the param_dist dictionary, where uniform and randint functions from the scipy.stats module specify the range of values for each hyperparameter. The RandomizedSearchCV class performs the random search cross-validation, sampling a specified number of combinations from the distribution. We obtain the best hyperparameters and performance score from the best_params_ and best_score_ attributes, and evaluate the best model on the test set.

### Conclusion
Hyperparameter tuning is a crucial step in optimizing the performance of neural networks. In this guide, we explored various techniques available in Keras for hyperparameter tuning. We discussed manual tuning, Grid Search, Random Search, and integration with Scikit-Learn for performing these techniques. By carefully tuning the hyperparameters, we can improve the accuracy and generalization of our models. Experimentation and iterative refinement of hyperparameters are key to finding the best configuration for our neural networks.