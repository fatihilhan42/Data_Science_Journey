## Here is some sample code using the Keras library:

```python 

import numpy as np
from tensorflow.keras.datasets import mnist
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense, Dropout
from tensorflow.keras.utils import to_categorical

# Load the MNIST dataset
(X_train, y_train), (X_test, y_test) = mnist.load_data()

# Flatten the input data to 1D arrays
X_train = X_train.reshape((X_train.shape[0], -1))
X_test = X_test.reshape((X_test.shape[0], -1))

# Normalize the input data to the range [0, 1]
X_train = X_train.astype('float32') / 255
X_test = X_test.astype('float32') / 255

# Convert the labels to one-hot encoded vectors
num_classes = 10
y_train = to_categorical(y_train, num_classes)
y_test = to_categorical(y_test, num_classes)

# Define the neural network model
model = Sequential()
model.add(Dense(256, activation='relu', input_shape=(784,)))
model.add(Dropout(0.2))
model.add(Dense(128, activation='relu'))
model.add(Dropout(0.2))
model.add(Dense(num_classes, activation='softmax'))

# Compile the model
model.compile(loss='categorical_crossentropy', optimizer='adam', metrics=['accuracy'])

# Train the model
model.fit(X_train, y_train, epochs=10, batch_size=128, validation_data=(X_test, y_test))

# Evaluate the model on the test data
score = model.evaluate(X_test, y_test, verbose=0)
print('Test loss:', score[0])
print('Test accuracy:', score[1])
```

**Test loss: 0.07131357491016388
Test accuracy: 0.9785000085830688**

In this example, we load the MNIST dataset and preprocess it by flattening the input images to 1D arrays and normalizing the pixel values to the range [0, 1]. We also convert the labels to one-hot encoded vectors. Then, we define a simple neural network with two hidden layers and train it on the dataset using the Adam optimizer and cross-entropy loss. Finally, we evaluate the trained model on the test data and print the test accuracy.


Here's another example of training a simple neural network for image classification using the popular CIFAR-10 dataset:

```python
import tensorflow as tf
from tensorflow.keras.datasets import cifar10

# Load CIFAR-10 dataset
(X_train, y_train), (X_test, y_test) = cifar10.load_data()

# Normalize pixel values to [0, 1]
X_train = X_train.astype('float32') / 255.0
X_test = X_test.astype('float32') / 255.0

# Define the model
model = tf.keras.Sequential([
    tf.keras.layers.Conv2D(32, (3, 3), activation='relu', input_shape=(32, 32, 3)),
    tf.keras.layers.MaxPooling2D((2, 2)),
    tf.keras.layers.Conv2D(64, (3, 3), activation='relu'),
    tf.keras.layers.MaxPooling2D((2, 2)),
    tf.keras.layers.Flatten(),
    tf.keras.layers.Dense(64, activation='relu'),
    tf.keras.layers.Dense(10, activation='softmax')
])

# Compile the model
model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])

# Train the model
model.fit(X_train, y_train, epochs=10, validation_data=(X_test, y_test))
```
Epoch 1/10
1563/1563 [==============================] - 40s 25ms/step - loss: 1.4727 - accuracy: 0.4685 - val_loss: 1.1694 - val_accuracy: 0.5846
Epoch 2/10
1563/1563 [==============================] - 40s 26ms/step - loss: 1.1074 - accuracy: 0.6108 - val_loss: 1.0255 - val_accuracy: 0.6470
Epoch 3/10
1563/1563 [==============================] - 36s 23ms/step - loss: 0.9895 - accuracy: 0.6522 - val_loss: 1.0044 - val_accuracy: 0.6570
Epoch 4/10
1563/1563 [==============================] - 38s 25ms/step - loss: 0.9069 - accuracy: 0.6827 - val_loss: 0.9792 - val_accuracy: 0.6610
Epoch 5/10
1563/1563 [==============================] - 41s 26ms/step - loss: 0.8444 - accuracy: 0.7067 - val_loss: 0.9665 - val_accuracy: 0.6685
Epoch 6/10
1563/1563 [==============================] - 44s 28ms/step - loss: 0.7830 - accuracy: 0.7273 - val_loss: 0.9179 - val_accuracy: 0.6872
Epoch 7/10
1563/1563 [==============================] - 44s 28ms/step - loss: 0.7319 - accuracy: 0.7455 - val_loss: 0.9012 - val_accuracy: 0.6945
Epoch 8/10
1563/1563 [==============================] - 45s 29ms/step - loss: 0.6887 - accuracy: 0.7614 - val_loss: 0.8988 - val_accuracy: 0.6976
Epoch 9/10
1563/1563 [==============================] - 45s 29ms/step - loss: 0.6473 - accuracy: 0.7723 - val_loss: 0.9042 - val_accuracy: 0.7052
Epoch 10/10
1563/1563 [==============================] - 41s 26ms/step - loss: 0.6105 - accuracy: 0.7867 - val_loss: 0.9206 - val_accuracy: 0.6950
<keras.callbacks.History at 0x1b372189c30>

**Source of dataset:** https://www.cs.toronto.edu/~kriz/cifar.html

This code loads the CIFAR-10 dataset and normalizes the pixel values to be in the range [0, 1]. It then defines a neural network model with two convolutional layers, two max pooling layers, and two dense layers, and compiles the model using the Adam optimizer and the sparse categorical cross-entropy loss function. Finally, the model is trained on the dataset for 10 epochs with a batch size of 32, and the validation accuracy is printed after each epoch.