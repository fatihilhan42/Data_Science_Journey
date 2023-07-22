Principal Component Analysis (PCA):

```python
from sklearn.decomposition import PCA

pca = PCA(n_components=2)
X_reduced = pca.fit_transform(X)

```

```python 
from sklearn.discriminant_analysis import LinearDiscriminantAnalysis

lda = LinearDiscriminantAnalysis(n_components=2)
X_reduced = lda.fit_transform(X, y)

```

```python
from sklearn.manifold import TSNE

tsne = TSNE(n_components=2)
X_reduced = tsne.fit_transform(X)

```

Autoencoders:

```python
from keras.layers import Input, Dense
from keras.models import Model

# Define the input layer
input_layer = Input(shape=(original_dim,))

# Define the encoding layer
encoded = Dense(encoding_dim, activation='relu')(input_layer)

# Define the decoding layer
decoded = Dense(original_dim, activation='sigmoid')(encoded)

# Create the autoencoder model
autoencoder = Model(input_layer, decoded)

# Compile the model
autoencoder.compile(optimizer='adam', loss='binary_crossentropy')

# Train the model
autoencoder.fit(X, X, epochs=10, batch_size=32)

```

These are just a few examples of dimensionality reduction techniques. Choose the appropriate technique based on your dataset and the goals of your analysis. Experiment with different techniques to find the best approach for your specific problem.