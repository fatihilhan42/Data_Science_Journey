# Scatter Plots
A scatter plot is a way to display data points on a 2-dimensional graph. It is used to show the relationship between two numerical variables. Scatter plots are often used to identify patterns and correlations in data, such as the relationship between a person's age and their income.

This folder contains examples and explanations of how to create scatter plots in Python using the matplotlib library. The examples will cover basic scatter plots, as well as how to customize the appearance of the plots.

## Creating a basic scatter plot
To create a basic scatter plot, you need to provide the x and y data for the plot, and then call the scatter function to create the plot. Here's an example:

```Python
import matplotlib.pyplot as plt

# Create some sample data
x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

# Create the scatter plot
plt.scatter(x, y)

# Add a title and axis labels
plt.title('Basic Scatter Plot Example')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')

# Show the plot
plt.show()
```
![1](https://user-images.githubusercontent.com/63750425/213683741-cccb24bb-28d6-4076-95fc-4ee74484001f.png)

This will create a basic scatter plot with the x and y data you provided. The title, xlabel, and ylabel functions are used to add a title and labels to the plot.

## Customizing the appearance
You can customize the appearance of the scatter plot by modifying the properties of the plot and the chart. For example, you can change the color and size of the markers, or add a grid.

```Python
import matplotlib.pyplot as plt

# Create some sample data
x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

# Create the scatter plot
plt.scatter(x, y, marker='x', s=50, color='red')

# Add a title and axis labels
plt.title('Customized Scatter Plot Example')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.grid()
# Show the plot
plt.show()
```
![2](https://user-images.githubusercontent.com/63750425/213683758-a59bb88e-1faa-40fa-b0dc-9197bc5ff70b.png)

In this example, the scatter plot is plotted using the scatter() function, with the following additional parameters:

marker='x': which sets the marker style to an "x" symbol.
s=50: which sets the size of the markers to 50 points.
color='red': which sets the color of the markers to red.


In addition to the above examples, you can also use colormap to map the data to a color, by using the c parameter and passing the data to map and cmap parameter to choose the colormap. Here's an example:


```Python
import matplotlib.pyplot as plt
import numpy as np

# Create some sample data
x = np.random.rand(50)
y = np.random.rand(50)
c = np.random.rand(50)

# Create the scatter plot
plt.scatter(x, y, c=c, cmap='viridis')

# Add a colorbar
plt.colorbar()

# Add a title and axis labels
plt.title('Scatter Plot with Colormap')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')

# Show the plot
plt.show()
```
![3](https://user-images.githubusercontent.com/63750425/213683781-363e84b9-aa7c-4daf-93b7-013ad488b001.png)

This will create a scatter plot where the color of the markers is determined by the values in the c array, and the colormap is set to viridis. The colorbar function is used to add a colorbar to the plot, which shows the mapping between the data values and the colors.

You can also use other properties and functions provided by matplotlib library to customize the appearance of the scatter plots and make it more informative and easy to understand.






