## Distance Metrics for k-Nearest Neighbors

The k-Nearest Neighbors (k-NN) algorithm relies on a distance metric to determine the similarity between two data points. The choice of distance metric can have a significant impact on the performance of the algorithm. Here are some commonly used distance metrics:

### Euclidean Distance
Euclidean distance is the most commonly used distance metric in k-NN. It measures the straight-line distance between two points in Euclidean space. For two points with coordinates $(x_1, y_1)$ and $(x_2, y_2)$, the Euclidean distance is given by:


$$ d_{E}(p, q) = \sqrt{(x_1 - x_2)^2 + (y_1 - y_2)^2} $$

In higher-dimensional spaces, the Euclidean distance formula becomes:

$$ d_{E}(p, q) = \sqrt{\sum_{i=1}^{n}(p_i - q_i)^2} $$

where $n$ is the number of dimensions.


### Manhattan Distance
Manhattan distance, also known as taxicab distance, is a distance metric that measures the distance between two points in a grid-like path. For two points with coordinates $(x_1, y_1)$ and $(x_2, y_2)$, the Manhattan distance is given by:

$$ d_{M}(p, q) = |x_1 - x_2| + |y_1 - y_2| $$

In higher-dimensional spaces, the Manhattan distance formula becomes:

$$ d_{M}(p, q) = \sum_{i=1}^{n}|p_i - q_i| $$


### Minkowski Distance
Minkowski distance is a generalization of both Euclidean and Manhattan distances. For two points with coordinates $(x_1, y_1)$ and $(x_2, y_2)$, the Minkowski distance of order $r$ is given by:

$$ d_{M}(p, q) = \left(\sum_{i=1}^{n}|p_i - q_i|^r\right)^{\frac{1}{r}} $$

When $r=1$, the Minkowski distance is equivalent to the Manhattan distance, and when $r=2$, it is equivalent to the Euclidean distance.

### Cosine Similarity
Cosine similarity is a distance metric commonly used in text classification and clustering. It measures the cosine of the angle between two vectors in a high-dimensional space. For two vectors $p$ and $q$, the cosine similarity is given by:

$$ \cos(\theta) = \frac{p \cdot q}{|p||q|} $$

where $\cdot$ denotes the dot product of the two vectors, and $|p|$ and $|q|$ denote their Euclidean norms.

### Hamming Distance
Hamming distance is a distance metric commonly used in information theory and coding. It measures the number of positions at which two binary strings differ. For two binary strings $p$ and $q$ of equal length $n$, the Hamming distance is given by:

$$ d_{H}(p, q) = \sum_{i=1}^{n}(p_i \oplus q_i) $$

where $\oplus$ denotes the exclusive or (XOR) operation.

These are just a few of the many distance metrics that can be used in k-NN. The choice of distance metric depends on the specific problem at hand and the characteristics of the data.