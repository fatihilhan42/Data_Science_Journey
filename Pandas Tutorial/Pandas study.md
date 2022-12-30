# Pandas

Welcome to the "Pandas" study of the "Pandas Tutorial" folder of the Data Science Journey repository! In this study, you will learn how to use the Pandas library for data manipulation and analysis in Python.

## Installation

To use Pandas, you will need to have it installed on your system. 
You can install Pandas using pip, the Python package manager:

```Python
pip install pandas
```


Alternatively, you can install Pandas using conda, the package manager for the Anaconda distribution of Python:

```Python
conda install pandas
```

## Data structures

Pandas has two primary data structures: the Series and the DataFrame.

A Series is a one-dimensional labeled array that can hold any data type. You can create a Series from a list or array like this:


```Python
import pandas as pd

s = pd.Series([1, 3, 5, np.nan, 6, 8])
print(s)
```

The above code will output the following Series:

```Python
0    1.0
1    3.0
2    5.0
3    NaN
4    6.0
5    8.0
dtype: float64
```


A DataFrame is a 2-dimensional labeled data structure with columns of potentially different types. 
You can create a DataFrame from a dictionary of lists,

```Python
df = pd.DataFrame({'A': [1, 2, 3, 4], 'B': [5, 6, 7, 8], 'C': [9, 10, 11, 12]})
```

The resulting DataFrame will have the following values:

```Python
   A  B   C
0  1  5   9
1  2  6  10
2  3  7  11
3  4  8  12
```

You can also create a DataFrame from a list of dictionaries, where each dictionary represents a row of the DataFrame and the keys of the dictionary represent the column names. For example:

```Python
df = pd.DataFrame([{'A': 1, 'B': 2, 'C': 3}, {'A': 4, 'B': 5, 'C': 6}])
```

```Python
   A  B  C
0  1  2  3
1  4  5  6
```


The resulting DataFrame will have the following values:

```Python
You can also create a DataFrame from a CSV file using the read_csv function:
```

```Python
df = pd.read_csv("data.csv")
print(df)
```


## Data manipulation
Once you have your data in a DataFrame, you can use various Pandas functions and methods to manipulate it. Some common tasks include:

- Selecting columns: You can select a single column of a DataFrame using the [] operator and the name of the column:

```Python
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6], 'C': [7, 8, 9]})
print(df['A'])
```

The above code will output the following Series:

```Python
0    1
1    2
2    3
Name: A, dtype: int64
```

You can also select multiple columns by passing a list of column names:

```Python
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6], 'C': [7, 8, 9]})
print(df[['A', 'C']])
```

The above code will output the following DataFrame:

```Python
   A
```


- Filtering rows: You can use a boolean condition to filter the rows of a DataFrame. For example:

```Python
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6], 'C': [7, 8, 9]})
print(df[df['A'] > 2])
```

The above code will output the following DataFrame:

```Python
   A  B  C
2  3  6  9
```

- Sorting rows: You can use the sort_values method to sort the rows of a DataFrame by one or more columns. For example:

```Python
df = pd.DataFrame({'A': [3, 2, 1], 'B': [6, 5, 4], 'C': [9, 8, 7]})
print(df.sort_values(by='A'))
```

The above code will output the following DataFrame:

```Python
   A  B  C
2  1  4  7
1  2  5  8
0  3  6  9
```

Aggregation: You can use the groupby method to group the rows of a DataFrame by one or more columns, and then apply an aggregation function to each group. For example:


```Python
df = pd.DataFrame({'A': [1, 1, 2, 2], 'B': [1, 2, 3, 4], 'C': [5, 6, 7, 8]})
```

This creates a DataFrame with 4 rows and 3 columns, with column names "A", "B", and "C". The values in the columns are:
```Python

   A  B  C
0  1  1  5
1  1  2  6
2  2  3  7
3  2  4  8
```

## Data manipulation
- Merging: You can use the merge function to merge two DataFrame objects based on a common column or set of columns. For example:

```Python
df1 = pd.DataFrame({'key': ['K0', 'K1', 'K2', 'K3'], 'A': ['A0', 'A1', 'A2', 'A3'], 'B': ['B0', 'B1', 'B2', 'B3']})
df2 = pd.DataFrame({'key': ['K0', 'K1', 'K2', 'K4'], 'C': ['C0', 'C1', 'C2', 'C3'], 'D': ['D0', 'D1', 'D2', 'D3']})
print(pd.merge(df1, df2, on='key'))
```

The above code will output the following DataFrame:

```Python

  key   A   B   C   D
0  K0  A0  B0  C0  D0
1  K1  A1  B1  C1  D1
2  K2  A2  B2  C2  D2
```


- Pivoting: You can use the pivot_table function to create a pivot table from a DataFrame. 
A pivot table is a summary of data that groups and aggregates data by one or more dimensions, and can be used to identify patterns and trends in the data. For example:

```Python
df = pd.DataFrame({'A': ['A0', 'A1', 'A2', 'A3'], 'B': ['B0', 'B1', 'B2', 'B3'], 'C': ['C0', 'C1', 'C2', 'C3'], 'D': ['D0', 'D1', 'D2', 'D3']})
print(df.pivot_table(index='A', columns='B', values='C', aggfunc='first'))
```

## Data visualization
Pandas integrates with several data visualization libraries, such as Matplotlib and Seaborn, to allow you to create various types of plots and charts from your data. Some common plots and charts you may want to create include:

Line plots: You can use the plot method to create a line plot of a Series or a DataFrame. For example:

```Python
import matplotlib.pyplot as plt

s = pd.Series([1, 3, 5, np.nan, 6, 8])
s.plot()
plt.show()

```
The above code will create a line plot of the Series:

![output](https://user-images.githubusercontent.com/63750425/210114887-4083e6e9-b26e-4d6b-b5b4-060af65244e8.png)

- Bar plots: You can use the plot.bar method to create a bar plot of a DataFrame. For example:

```Python
import matplotlib.pyplot as plt

df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})
df.plot.bar()
plt.show()
```

The above code will create a bar plot of the DataFrame:

![output2](https://user-images.githubusercontent.com/63750425/210114903-415e3ebc-6ff0-4b66-b7f0-0e5568b84d3a.png)


- Histograms: You can use the plot.hist method to create a histogram of a Series. A histogram is a graphical representation of the distribution of a dataset, and can be used to identify patterns and outliers in the data. For example:

```Python
import matplotlib.pyplot as plt

s = pd.Series([1, 3, 5, np.nan, 6, 8])
s.plot.hist()
plt.show()
```

The above code will create a histogram of the Series:

![output3](https://user-images.githubusercontent.com/63750425/210114924-db818bcd-76a8-456c-8104-487ebd8195d1.png)

There are many other types of plots and charts you can create using Pandas and its visualization libraries. I encourage you to explore the documentation and try creating different types of plots to gain a deeper understanding of your data.


That concludes the "Pandas" study. I hope you have learned how to use the Pandas library for data manipulation and visualization in Python.
