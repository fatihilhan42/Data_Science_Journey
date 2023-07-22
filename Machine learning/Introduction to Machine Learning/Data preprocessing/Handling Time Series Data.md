Time Series Visualization:

```python

import pandas as pd
import matplotlib.pyplot as plt

# Load time series data
data = pd.read_csv('data.csv', parse_dates=['date'], index_col='date')

# Plot the time series
plt.plot(data)
plt.xlabel('Date')
plt.ylabel('Value')
plt.title('Time Series Data')
plt.show()
```

Resampling Time Series Data:

```python
# Resample the data to a lower frequency (e.g., monthly)
monthly_data = data.resample('M').mean()

# Resample the data to a higher frequency (e.g., daily)
daily_data = data.resample('D').ffill()

```

Rolling Window Statistics:
```python
# Compute the rolling mean of the time series
rolling_mean = data.rolling(window=7).mean()

# Compute the rolling standard deviation of the time series
rolling_std = data.rolling(window=7).std()

```

Time Series Decomposition:
```python
from statsmodels.tsa.seasonal import seasonal_decompose

# Perform time series decomposition
decomposition = seasonal_decompose(data)

# Extract the trend, seasonal, and residual components
trend = decomposition.trend
seasonal = decomposition.seasonal
residual = decomposition.resid

```

These are just a few examples of how to handle time series data. The specific techniques and approaches may vary depending on the nature of the time series and the analysis you want to perform.