## Activation Functions
In a neural network, an activation function is a function that is applied to the output of a layer of neurons. The purpose of the activation function is to introduce non-linearity into the output of a neural network, which allows the network to model more complex relationships between inputs and outputs. Without an activation function, the output of the neural network would be a simple linear combination of its inputs, and the network would be limited to modeling only linear relationships.

There are several different types of activation functions that are commonly used in neural networks. In this file, we will discuss some of the most popular ones: Sigmoid, ReLU, and Softmax.

Sigmoid Function
The Sigmoid function is a non-linear function that maps any input value to a value between 0 and 1. It is commonly used as an activation function in the output layer of a binary classification model, where the goal is to predict a probability that an input belongs to one of two classes.

The formula for the Sigmoid function is:
```python
sigmoid(x) = 1 / (1 + e^-x)
```

where 'x' is the input to the function. The output of the function is always between 0 and 1.

The Sigmoid function has some drawbacks, however. One issue is that its output saturates when its input is very positive or very negative, meaning that the gradient of the function becomes very small in these regions. This can cause issues with the training of deep neural networks.

### ReLU Function
The Rectified Linear Unit (ReLU) function is a non-linear function that is commonly used as an activation function in neural networks. The ReLU function is defined as:
```python
relu(x) = max(0, x)
```

where 'x' is the input to the function. The output of the function is the maximum of 0 and the input 'x'.

One advantage of the ReLU function is that it is very simple to compute and does not saturate in the same way as the Sigmoid function. However, it has been observed that ReLU can lead to dead neurons, where the output of a neuron is always 0, and the gradient of the function is also 0. This can occur when the input to the ReLU function is negative, and can make it difficult to train a neural network.

### Softmax Function
The Softmax function is a generalization of the Sigmoid function to multiple classes. It is commonly used as an activation function in the output layer of a multi-class classification model, where the goal is to predict the probability of an input belonging to each of several possible classes.

The formula for the Softmax function is:

```python 
softmax(x_i) = e^(x_i) / sum(e^(x_j))
```

where 'x_i' is the input to the function for class 'i', and the sum is taken over all possible classes. The output of the function is a probability distribution over the possible classes, with each class having a probability between 0 and 1, and the sum of the probabilities adding up to 1.

The Softmax function is useful for multi-class classification tasks, but it has some of the same drawbacks as the Sigmoid function, such as saturation and vanishing gradients. However, there are variants of the Softmax function, such as the Sparsemax function, that can address some of these issues.

### Conclusion
Activation functions are a crucial component of neural networks, and choosing the right activation function can be an important factor in achieving good performance. There are many other activation functions besides the ones discussed here, and different activation functions may be more or less suitable for different types of tasks.