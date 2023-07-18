1. Standardization (Z-score normalization):

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
scaled_data = scaler.fit_transform(data)

```

2. Min-Max Scaling (Normalization):

```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()
scaled_data = scaler.fit_transform(data)

```

3. Robust Scaling:

```python
from sklearn.preprocessing import RobustScaler

scaler = RobustScaler()
scaled_data = scaler.fit_transform(data)

```

4. Max Abs Scaling:

```python
from sklearn.preprocessing import MaxAbsScaler

scaler = MaxAbsScaler()
scaled_data = scaler.fit_transform(data)

```

5. Power Transformation:

```pythom
from sklearn.preprocessing import PowerTransformer

scaler = PowerTransformer(method='yeo-johnson')
scaled_data = scaler.fit_transform(data)

```

6. Quantile Transformation:
```python
from sklearn.preprocessing import QuantileTransformer

scaler = QuantileTransformer(output_distribution='normal')
scaled_data = scaler.fit_transform(data)

```

Note: In the code examples, data refers to the input data that you want to scale. Replace it with your own data.

Each scaling technique has its own advantages and considerations. Choose the appropriate scaling method based on your data distribution and the requirements of your machine learning algorithm.

Remember to fit the scaler on the training data and use the same scaler to transform the test or new data to ensure consistency in scaling.