# Matplotlib Tutorial

Welcome to the "Matplotlib Tutorial" of the "Introduction to Data Science in Python" folder of the Data Science Journey repository! In this tutorial, you will learn how to use the Matplotlib library for data visualization in Python.

## Installation
To use Matplotlib, you will need to have it installed on your system. You can install Matplotlib using pip, the Python package manager:


pip install matplotlib


Alternatively, you can install Matplotlib using conda, the package manager for the Anaconda distribution of Python:


conda install matplotlib


## Importing and using Matplotlib

To use Matplotlib in your Python code, you will need to import it using the following import statement:


import matplotlib.pyplot as plt


This import statement creates an alias plt for the pyplot module of Matplotlib, which provides a high-level interface for creating plots and charts.


## Line plots

One of the most common types of plots in Matplotlib is the line plot. You can create a line plot using the plot function of the pyplot module. For example:


import matplotlib.pyplot as plt

# Create some data
x = [1, 2, 3, 4]
y = [1, 4, 9, 16]

# Create a line plot
plt.plot(x, y)

# Show the plot
plt.show()

The above code will create a line plot of the data:

RESİM GELECEK.

You can also customize the appearance of the line plot by setting various properties of the plot function. For example:


import matplotlib.pyplot as plt

# Create some data
x = [1, 2, 3, 4]
y = [1, 4, 9, 16]

# Create a line plot
plt.plot(x, y, color='red', linewidth=2, linestyle='dashed', marker='o', markersize=8)

# Show the plot
plt.show()

The above code will create a line plot with a red dashed line and circles as markers:

rESİM gELECEK.


## Scatter plots

Another common type of plot in Matplotlib is the scatter plot. You can create a scatter plot using the scatter function of the pyplot module. For example:



import matplotlib.pyplot as plt

# Create some data
x = [1, 2, 3, 4]
y = [1, 4, 9, 16]

# Create a scatter plot
plt.scatter(x, y)

# Show the plot
plt.show()



The above code will create a scatter plot of the data:


Resim GELECEK.



Like with line plots, you can customize the appearance of the scatter plot by setting various properties of the scatter function. For example:



import matplotlib.pyplot as plt

# Create some data
x = [1, 2, 3, 4]
y = [1, 4, 9, 16]

# Create a scatter plot
plt.scatter(x, y, color='green', marker='x', s=100)

# Show the plot
plt.show()



The above code will create a scatter plot with green crosses as markers:


rESİM gELECEK


## Bar plots
Bar plots are used to visualize data in the form of vertical or horizontal bars. You can create a bar plot using the bar function of the pyplot module. For example:

import matplotlib.pyplot as plt

# Create some data
x = [1, 2, 3, 4]
y = [1, 4, 9, 16]

# Create a bar plot
plt.bar(x, y)

# Show the plot
plt.show()



The above code will create a bar plot of the data:

RESİM GELECEK

You can also customize the appearance of the bar plot by setting various properties of the bar function. For example:

import matplotlib.pyplot as plt

# Create some data
x = [1, 2, 3, 4]
y = [1, 4, 9, 16]

# Create a bar plot
plt.bar(x, y, color='pink', alpha=0.5, width=0.5)

# Show the plot
plt.show()


The above code will create a bar plot with pink, semi-transparent bars that are slightly narrower than the default width:

RESİM GELECEK


## Pie charts
Pie charts are used to visualize data in the form of a circle divided into slices. You can create a pie chart using the pie function of the pyplot module. For example:


import matplotlib.pyplot as plt

# Create some data
sizes = [10, 20, 30, 40]
labels = ['A', 'B', 'C', 'D']

# Create a pie chart
plt.pie(sizes, labels=labels)

# Show the plot
plt.show()




The above code will create a pie chart of the data:

RESİM GELECEK

Like with other types of plots, you can customize the appearance of the pie chart by setting various properties of the pie function. For example:


import matplotlib.pyplot as plt

# Create some data
sizes = [10, 20, 30, 40]
labels = ['A', 'B', 'C', 'D']

# Create a pie chart
plt.pie(sizes, labels=labels, explode=[0, 0.1, 0, 0], shadow=True, autopct='%1.1f%%')

# Show the plot
plt.show()


The above code will create a pie chart with a "exploded" slice and percentage labels:

RESİM GELECEK



## Other types of plots
In addition to the types of plots covered in this tutorial, Matplotlib offers many other types of plots and charts you can create. Some examples include:

Box plots: used to visualize the distribution of a dataset
Violin plots: similar to box plots, but with a rotated kernel density plot on each side
Stem plots: used to plot discrete data in a way that emphasizes the underlying structure
Quiver plots: used to visualize vector fields
I encourage you to explore the documentation and try creating different types of plots to gain a deeper understanding of your data.

I hope this tutorial has been helpful in introducing you to the Matplotlib library for data visualization in Python.



