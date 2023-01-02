# Seaborn Tutorial
Welcome to the "Seaborn Tutorial" of the "Introduction to Data Science in Python" folder of the Data Science Journey repository! In this tutorial, you will learn how to use the Seaborn library for data visualization in Python.

## Installation

To use Seaborn, you will need to have it installed on your system. You can install Seaborn using pip, the Python package manager:

```Python
pip install seaborn
```

Alternatively, you can install Seaborn using conda, the package manager for the Anaconda distribution of Python:

```Python
conda install seaborn
```

## Importing and using Seaborn
To use Seaborn in your Python code, you will need to import it using the following import statement:

```Python
import seaborn as sns
```

This import statement creates an alias sns for the Seaborn library.


## Line plots
One of the most common types of plots in Seaborn is the line plot. You can create a line plot using the lineplot function of the sns module. For example:

```Python
import seaborn as sns

# Create some data
x = [1, 2, 3, 4]
y = [1, 4, 9, 16]

# Create a line plot
sns.lineplot(x, y)
```

The above code will create a line plot of the data:

RESİM GELECEK.


You can also customize the appearance of the line plot by setting various parameters of the lineplot function. For example:

```Python
import seaborn as sns

# Create some data
x = [1, 2, 3, 4]
y = [1, 4, 9, 16]

# Create a line plot
sns.lineplot(x, y, color='red', style='dashed', markers=True)
```

The above code will create a line plot with a red dashed line and markers:

RESİM GELECEK.


## Scatter plots

Another common type of plot in Seaborn is the scatter plot. You can create a scatter plot using the scatterplot function of the sns module. For example:

```Python
import seaborn as sns

# Create some data
x = [1, 2, 3, 4]
y = [1, 4, 9, 16]

# Create a scatter plot
sns.scatterplot(x, y)
```

The above code will create a scatter plot of the data:

RESİM GELECEK.


Like with line plots, you can customize the appearance of the scatter plot by setting various parameters of the scatterplot function. For example:

```Python
import seaborn as sns

# Create some data
x = [1, 2, 3, 4]
y = [1, 4, 9, 16]

# Create a scatter plot
sns.scatterplot(x, y, color='green', marker='x', size=200)
```

RESİM GELECEK.


## Bar plots
Bar plots are used to visualize data in the form of vertical or horizontal bars. You can create a bar plot using the barplot function of the sns module. For example:

```Python
import seaborn as sns

# Create some data
x = ['A', 'B', 'C', 'D']
y = [1, 4, 9, 16]

# Create a bar plot
sns.barplot(x, y)
```

The above code will create a bar plot of the data:


RESİM GELECEK.




You can also customize the appearance of the bar plot by setting various parameters of the barplot function. For example:

```Python
import seaborn as sns

# Create some data
x = ['A', 'B', 'C', 'D']
y = [1, 4, 9, 16]

# Create a bar plot
sns.barplot(x, y, color='pink', alpha=0.5, estimator=np.mean)
```

The above code will create a bar plot with pink, semi-transparent bars that display the mean of the data rather than the default estimate (which is the standard error of the mean):

RESİM GELECEK


## Box plots
Box plots are used to visualize the distribution of a dataset. You can create a box plot using the boxplot function of the sns module. For example:

```Python
import seaborn as sns
import numpy as np

# Create some data
data = np.random.normal(size=(20, 6))

# Create a box plot
sns.boxplot(data=data)
```


The above code will create a box plot of the data:

RESİM GELECEK.

You can also customize the appearance of the box plot by setting various parameters of the boxplot function. For example:

```Python
import seaborn as sns
import numpy as np

# Create some data
data = np.random.normal(size=(20, 6))

# Create a box plot
sns.boxplot(data=data, orient='horizontal', palette='coolwarm')
```


The above code will create a horizontal box plot with a coolwarm color palette:


RESİM GELECEK.



## Violin plots
Violin plots are similar to box plots, but with a rotated kernel density plot on each side. You can create a violin plot using the violinplot function of the sns module. For example:


```Python
import seaborn as sns
import numpy as np

# Create some data
data = np.random.normal(size=(20, 6))

# Create a violin plot
sns.violinplot(data=data)

```

The above code will create a violin plot of the data:


RESİM GELECEK.

You can customize the appearance of a violin plot in Seaborn by setting various parameters of the violinplot function.

Here is an example of customizing the appearance of a violin plot in Seaborn:

```Python
import seaborn as sns
import numpy as np

# Create some data
data = np.random.normal(size=(20, 6))

# Create a violin plot
sns.violinplot(data=data, orient='horizontal', palette='coolwarm', inner='stick')
```

The above code will create a horizontal violin plot with a coolwarm color palette and stick plot inside:

RESİM GELECEK.

## Heatmaps
Heatmaps are used to visualize data in the form of a color-coded grid. You can create a heatmap using the heatmap function of the sns module. For example:

```Python
import seaborn as sns
import numpy as np

# Create some data
data = np.random.normal(size=(10, 10))

# Create a heatmap
sns.heatmap(data)
```

The above code will create a heatmap of the data:

RESİM GELECEK.


You can also customize the appearance of the heatmap by setting various parameters of the heatmap function. For example:

```Python
import seaborn as sns
import numpy as np

# Create some data
data = np.random.normal(size=(10, 10))

# Create a heatmap
sns.heatmap(data, cmap='Reds', annot=True, fmt='.1f', vmin=0, vmax=1)
```

The above code will create a heatmap with a red color map, annotations displaying the data values, a floating-point format of .1f, and a minimum and maximum value of 0 and 1, respectively:

RESİM GELECEK


## Pair plots
Pair plots are used to visualize relationships between multiple variables in a dataset. You can create a pair plot using the pairplot function of the sns module. For example:

```Python
import seaborn as sns
import numpy as np
import pandas as pd

# Create some data
data = np.random.normal(size=(20, 3))
df = pd.DataFrame(data, columns=['A', 'B', 'C'])

# Create a pair plot
sns.pairplot(df)
```


The above code will create a pair plot of the data:

RESİM GELECEK.


You can also customize the appearance of the pair plot by setting various parameters of the pairplot function. For example:

```Python
import seaborn as sns
import numpy as np
import pandas as pd

# Create some data
data = np.random.normal(size=(20, 3))
df = pd.DataFrame(data, columns=['A', 'B', 'C'])

# Create a pair plot
sns.pairplot(df, hue='B', palette='coolwarm', diag_kind='hist')
```


The above code will create a pair plot with a coolwarm color palette, colored by the 'B' column, and histograms on the diagonal:

RESİM GELECEK.

## Conclusion

I hope this Seaborn tutorial was helpful in introducing you to the Seaborn library for data visualization in Python. Seaborn offers a wide range of plotting functions that can be used for visualizing various types of data. By setting various parameters of the plotting functions, you can customize the appearance of the plots to suit your needs.