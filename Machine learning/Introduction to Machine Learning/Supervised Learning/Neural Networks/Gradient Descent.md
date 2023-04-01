## Gradient Descent
Gradient descent is an optimization algorithm commonly used in neural networks for training purposes. The goal of training is to find the weights and biases of a neural network that minimize the cost function, which measures how well the neural network is performing on the given task. The cost function is defined based on the difference between the expected output and the actual output of the neural network for a given input.

The gradient descent algorithm iteratively adjusts the weights and biases of the neural network to minimize the cost function. The algorithm works by computing the gradient of the cost function with respect to each weight and bias, and then adjusting the weights and biases in the direction of the negative gradient. This process continues until the algorithm converges to a minimum of the cost function.

There are two main types of gradient descent: batch gradient descent and stochastic gradient descent.

### Batch Gradient Descent
Batch gradient descent computes the gradient of the cost function with respect to each weight and bias using the entire training dataset. This can be computationally expensive for large datasets, but it guarantees that the algorithm is moving in the direction of the steepest descent.

The update rule for batch gradient descent is given by:

```python 
w = w - alpha * dw
b = b - alpha * db
```

where w and b are the weights and biases of the neural network, alpha is the learning rate (a hyperparameter that controls the step size of the updates), dw and db are the gradients of the cost function with respect to w and b, respectively.

### Stochastic Gradient Descent
Stochastic gradient descent computes the gradient of the cost function with respect to each weight and bias using a single training example at a time. This can be computationally more efficient than batch gradient descent for large datasets, but the updates can be noisy and may not always move in the direction of the steepest descent.

The update rule for stochastic gradient descent is given by:

```python 
w = w - alpha * dw_i
b = b - alpha * db_i
```

where dw_i and db_i are the gradients of the cost function with respect to w and b for the i-th training example, respectively.

### Mini-Batch Gradient Descent
Mini-batch gradient descent is a compromise between batch gradient descent and stochastic gradient descent. It computes the gradient of the cost function with respect to each weight and bias using a small batch of training examples at a time. This can be computationally efficient and less noisy than stochastic gradient descent, while still moving in the direction of the steepest descent.

The update rule for mini-batch gradient descent is given by:

```python 
w = w - alpha * dw_batch
b = b - alpha * db_batch
```

where dw_batch and db_batch are the average gradients of the cost function with respect to w and b for the batch of training examples.

### Choosing the Learning Rate
The learning rate alpha is a hyperparameter that controls the step size of the updates. If the learning rate is too large, the updates may overshoot the minimum of the cost function and the algorithm may fail to converge. If the learning rate is too small, the algorithm may take a long time to converge.

There are several methods for choosing the learning rate, including grid search, random search, and adaptive methods such as AdaGrad and Adam.

### Momentum
Momentum is a technique that can be used to speed up convergence of the gradient descent algorithm. It works by adding a fraction of the previous weight update to the current weight update, effectively creating a rolling average of the weight