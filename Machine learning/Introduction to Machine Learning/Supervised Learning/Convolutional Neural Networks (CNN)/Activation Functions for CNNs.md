## Activation Functions for CNNs

Activation functions play a critical role in convolutional neural networks (CNNs) by introducing nonlinearity and allowing the network to learn complex relationships between inputs and outputs. In this file, we will discuss some of the most commonly used activation functions in CNNs.

**1. ReLU (Rectified Linear Unit):**
The ReLU activation function is defined as:

f(x) = max(0, x)

ReLU is the most commonly used activation function in CNNs. It is computationally efficient and has been shown to work well in practice. ReLU is non-linear and introduces nonlinearity to the network, which is necessary to learn complex relationships between inputs and outputs.

**2. Sigmoid:**

The sigmoid activation function is defined as:
f(x) = 1 / (1 + e^(-x))

Sigmoid is a smooth, S-shaped function that is commonly used as an activation function in the output layer of binary classification problems. It squashes the output to the range [0, 1], which can be interpreted as a probability.

**3. Tanh:**

The tanh activation function is defined as:
f(x) = (e^x - e^(-x)) / (e^x + e^(-x))

Tanh is similar to the sigmoid function, but it squashes the output to the range [-1, 1]. It is also smooth and introduces nonlinearity to the network.

**4. Softmax:**

The softmax activation function is commonly used in the output layer of multi-class classification problems. It converts the output of the network to a probability distribution over the classes. The softmax function is defined as:
f(x_i) = e^(x_i) / sum(e^(x_j))

Where x_i is the input to the i-th neuron in the layer and sum(e^(x_j)) is the sum of the exponential of all the inputs in the layer.

**5. Leaky ReLU:**

The Leaky ReLU activation function is defined as:
f(x) = x if x > 0, else ax

where a is a small constant, typically 0.01. Leaky ReLU addresses the "dying ReLU" problem, where some ReLU neurons may become inactive during training and never activate again. By introducing a small slope for negative values, Leaky ReLU allows gradients to flow even when the neuron is not active.

**6. ELU (Exponential Linear Unit):**

The ELU activation function is defined as:
f(x) = x if x > 0, else alpha * (e^x - 1)

where alpha is a small constant, typically 1. ELU is similar to Leaky ReLU in that it addresses the "dying ReLU" problem. Additionally, ELU has been shown to improve the performance of CNNs compared to ReLU.

These are some of the most commonly used activation functions in CNNs. Choosing the right activation function is an important consideration when designing a CNN, and can have a significant impact on its performance.
