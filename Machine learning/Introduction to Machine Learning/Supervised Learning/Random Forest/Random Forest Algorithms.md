1. **Classification and Regression Tree (CART):** This algorithm is the most commonly used algorithm for building decision trees, which are the building blocks of random forests. CART is used to split a dataset into smaller subsets by selecting the best feature that gives the most homogeneous subsets.

2- **ID3 (Iterative Dichotomiser 3):** This algorithm is used to build decision trees by selecting the best attribute to split the dataset at each node based on information gain. It is used for categorical data.

3- **C4.5:** This algorithm is an extension of the ID3 algorithm and is also used for building decision trees. It can handle both categorical and continuous data.

4- **Random subspace method (RSS):** This algorithm randomly selects a subset of features to use for building each tree in the random forest. This is useful for reducing the correlation between the trees and improving the generalization ability of the model.

5- **Random projection (RP):** This algorithm randomly projects the data onto a lower dimensional subspace before building each tree in the random forest. This is also useful for reducing the correlation between the trees and improving the generalization ability of the model.

6- **Gradient Boosting:** This algorithm builds a set of decision trees in a sequential manner, with each subsequent tree trying to correct the errors made by the previous tree. This results in a highly accurate model but can be computationally expensive.