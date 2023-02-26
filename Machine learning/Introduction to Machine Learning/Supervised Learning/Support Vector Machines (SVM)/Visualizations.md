## Visualizations 

```python 
import numpy as np
import matplotlib.pyplot as plt
from sklearn import svm, datasets

# Load the iris dataset
iris = datasets.load_iris()
X = iris.data[:, :2]  # we only take the first two features
y = iris.target

# Create an instance of SVM and fit the data
C = 1.0  # SVM regularization parameter
clf = svm.SVC(kernel='linear', C=C)
clf.fit(X, y)

# Create a mesh to plot in
h = 0.02  # step size in the mesh
x_min, x_max = X[:, 0].min() - 0.5, X[:, 0].max() + 0.5
y_min, y_max = X[:, 1].min() - 0.5, X[:, 1].max() + 0.5
xx, yy = np.meshgrid(np.arange(x_min, x_max, h), np.arange(y_min, y_max, h))

# Plot the decision boundary
Z = clf.predict(np.c_[xx.ravel(), yy.ravel()])  # make predictions for all points in the mesh
Z = Z.reshape(xx.shape)
plt.contourf(xx, yy, Z, cmap=plt.cm.Paired, alpha=0.8)

# Plot the training points
plt.scatter(X[:, 0], X[:, 1], c=y, cmap=plt.cm.Paired)
plt.xlabel('Sepal length')
plt.ylabel('Sepal width')
plt.xlim(xx.min(), xx.max())
plt.ylim(yy.min(), yy.max())
plt.xticks(())
plt.yticks(())
plt.title('SVM classification of Iris dataset')

plt.show()
```
1.resim 

### A visualization of how SVMs work for binary classification tasks.
2.resim 

In this visualization, the blue and red points represent the two classes that we want to separate. The black line represents the decision boundary of the SVM classifier, and the dashed lines represent the margin. The margin is the distance between the decision boundary and the closest data points from each class.

The goal of the SVM algorithm is to find the decision boundary that maximizes the margin between the two classes. This decision boundary is also called the maximum margin hyperplane. In the image above, the SVM has found a decision boundary that maximizes the margin between the two classes.

When new data points are introduced, the SVM classifier will predict which class they belong to based on which side of the decision boundary they fall on.

### A visualization of the kernel trick and how it can be used to transform data into a higher-dimensional space
```python 

import numpy as np
import matplotlib.pyplot as plt
from sklearn.datasets import make_circles
from sklearn.svm import SVC

# Generate toy data with two classes that are not linearly separable
X, y = make_circles(n_samples=100, noise=0.1, factor=0.5, random_state=42)

# Define a function to plot the data and decision boundary
def plot_data_and_boundary(model, X, y):
    # Create a mesh of points to plot in
    xx, yy = np.meshgrid(np.linspace(-1.5, 1.5, 100),
                         np.linspace(-1.5, 1.5, 100))
    # Predict the class of each point in the mesh
    Z = model.predict(np.c_[xx.ravel(), yy.ravel()])
    Z = Z.reshape(xx.shape)
    # Plot the data points and decision boundary
    plt.contourf(xx, yy, Z, cmap=plt.cm.RdBu, alpha=0.6)
    plt.scatter(X[:, 0], X[:, 1], c=y, cmap=plt.cm.RdBu, edgecolors='k')
    plt.xlabel('Feature 1')
    plt.ylabel('Feature 2')

# Define an SVM with a linear kernel and fit it to the data
linear_svm = SVC(kernel='linear', C=10)
linear_svm.fit(X, y)

# Define an SVM with an RBF kernel and fit it to the data
rbf_svm = SVC(kernel='rbf', C=10, gamma=1)
rbf_svm.fit(X, y)

# Plot the data and decision boundaries for the linear SVM
plt.subplot(121)
plot_data_and_boundary(linear_svm, X, y)
plt.title('Linear SVM')

# Plot the data and decision boundaries for the RBF SVM
plt.subplot(122)
plot_data_and_boundary(rbf_svm, X, y)
plt.title('RBF SVM with gamma=1')

plt.show()

```
3.resim

In this example, we generate toy data with two classes that are not linearly separable using the **make_circles** function from scikit-learn. We then define two SVMs: one with a linear kernel and one with an RBF (radial basis function) kernel. The linear SVM tries to find a linear decision boundary that separates the two classes, while the RBF SVM uses a non-linear kernel to transform the data into a higher-dimensional space where a linear boundary can be found.

We plot the data and decision boundaries for both SVMs using the **plot_data_and_boundary** function, which takes a trained SVM and the input data and produces a plot that shows the data points and the decision boundary.

The resulting plot shows that the linear SVM is not able to separate the two classes, while the RBF SVM with a gamma value of 1 is able to find a non-linear decision boundary that separates the two classes. This is an example of how the kernel trick can be used to transform data into a higher-dimensional space where a linear boundary can be found.


```python 
import numpy as np
import matplotlib.pyplot as plt
from sklearn import datasets, svm

# Load the iris dataset
iris = datasets.load_iris()

# Extract the first two features
X = iris.data[:, :2]
y = iris.target

# Create an SVM classifier with a linear kernel
clf = svm.SVC(kernel='linear', C=1000)

# Fit the classifier to the data
clf.fit(X, y)

# Create a meshgrid of points to visualize the decision boundaries
x_min, x_max = X[:, 0].min() - 1, X[:, 0].max() + 1
y_min, y_max = X[:, 1].min() - 1, X[:, 1].max() + 1
xx, yy = np.meshgrid(np.arange(x_min, x_max, 0.01),
                     np.arange(y_min, y_max, 0.01))
Z = clf.predict(np.c_[xx.ravel(), yy.ravel()])
Z = Z.reshape(xx.shape)

# Plot the decision boundaries
plt.contourf(xx, yy, Z, cmap=plt.cm.Paired, alpha=0.8)

# Plot the training points
plt.scatter(X[:, 0], X[:, 1], c=y, cmap=plt.cm.Paired)

# Set axis labels and title
plt.xlabel('Sepal length')
plt.ylabel('Sepal width')
plt.title('SVM decision boundaries on the iris dataset')

# Show the plot
plt.show()
```
4.resim 

This code will create a plot that shows the decision boundaries created by the SVM classifier for the iris dataset. The x-axis represents sepal length and the y-axis represents sepal width, and each point in the plot represents an iris flower. The color of each point indicates its class (setosa, versicolor, or virginica). The shaded regions represent the regions of the feature space that are classified as belonging to each class by the SVM.