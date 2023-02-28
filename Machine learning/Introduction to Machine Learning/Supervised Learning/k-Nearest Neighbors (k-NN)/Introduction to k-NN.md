# Introduction to k-Nearest Neighbors (k-NN)

k-Nearest Neighbors (k-NN) is a non-parametric machine learning algorithm that can be used for both regression and classification tasks. Given a new observation, k-NN searches the training set for the k closest instances and returns their average for regression or the mode for classification. The distance metric used to define "closeness" can vary, but the most common distance metrics are Euclidean distance and Manhattan distance.

k-NN is a simple yet effective algorithm that is often used as a baseline model to compare the performance of more complex algorithms. It is especially useful when the decision boundary is highly irregular, but it can also suffer from the curse of dimensionality when the number of features is large.

In this folder, we will cover the basics of k-NN, how to implement it using Python's Scikit-Learn library, how to tune hyperparameters using cross-validation, and some best practices for using k-NN in practice.