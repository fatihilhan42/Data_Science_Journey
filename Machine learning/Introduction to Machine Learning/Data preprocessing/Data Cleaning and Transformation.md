```python
import pandas as pd

# Load the dataset
data = pd.read_csv('data.csv')

# Cleaning missing values
data['age'].fillna(data['age'].mean(), inplace=True)
data['income'].fillna(data['income'].median(), inplace=True)
data['education'].fillna('Unknown', inplace=True)

# Encoding categorical variables
data['gender'] = data['gender'].map({'Male': 0, 'Female': 1})
data = pd.get_dummies(data, columns=['education'])

# Scaling numerical variables
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()
data['age'] = scaler.fit_transform(data['age'].values.reshape(-1, 1))
data['income'] = scaler.fit_transform(data['income'].values.reshape(-1, 1))

# Handling outliers
def remove_outliers(data, column, threshold=3):
    z_scores = (data[column] - data[column].mean()) / data[column].std()
    data = data.loc[abs(z_scores) <= threshold]
    return data

data = remove_outliers(data, 'income')

# Feature engineering
data['age_squared'] = data['age']**2
data['income_log'] = np.log1p(data['income'])

# Dropping unnecessary columns
data = data.drop(['education_Unknown'], axis=1)

# Checking the cleaned and transformed data
print(data.head())

```
In this example, we perform various data cleaning and transformation steps:

1. Cleaning missing values: We fill missing values in the 'age' column with the mean, 'income' column with the median, and 'education' column with 'Unknown' label using the fillna() function.

2. Encoding categorical variables: We convert the 'gender' column from 'Male' and 'Female' to numeric values (0 and 1) using the **map()** function. We also one-hot encode the 'education' column using the **get_dummies()** function to create binary indicator variables.

3. Scaling numerical variables: We use the **MinMaxScaler()** to scale the 'age' and 'income' columns to a specified range (usually [0, 1]).

4. andling outliers: We define a function **remove_outliers()** that uses z-scores to identify and remove outliers in the 'income' column.

5. Feature engineering: We create new features by squaring the 'age' column and taking the natural logarithm of the 'income' column.

6. Dropping unnecessary columns: We drop the 'education_Unknown' column as it is no longer needed.

Finally, we print the cleaned and transformed dataset using **print(data.head())**.

Remember to adapt the code to your specific dataset and requirements.