Concatenation:

```python
import pandas as pd

# Load the data from different sources
data1 = pd.read_csv('data1.csv')
data2 = pd.read_csv('data2.csv')

# Concatenate the data vertically (row-wise)
concatenated_data = pd.concat([data1, data2], axis=0)

```

```python
import pandas as pd

# Load the data with common key columns
data1 = pd.read_csv('data1.csv')
data2 = pd.read_csv('data2.csv')

# Merge the data based on common key columns
merged_data = pd.merge(data1, data2, on='key_column')

```

Reshaping:

```python
import pandas as pd

# Load the data with a wide format
wide_data = pd.read_csv('wide_data.csv')

# Reshape the data from wide to long format
long_data = pd.melt(wide_data, id_vars=['id'], var_name='variable', value_name='value')

```

Scaling and Normalization:

```python
from sklearn.preprocessing import MinMaxScaler, StandardScaler

# Load the data
data = pd.read_csv('data.csv')

# Scale the data using Min-Max scaling
scaler = MinMaxScaler()
scaled_data = scaler.fit_transform(data)

# Normalize the data using z-score normalization
normalizer = StandardScaler()
normalized_data = normalizer.fit_transform(data)
```

These are just a few examples of data integration and transformation techniques. The specific techniques and approaches may vary depending on the specific requirements and characteristics of your data.