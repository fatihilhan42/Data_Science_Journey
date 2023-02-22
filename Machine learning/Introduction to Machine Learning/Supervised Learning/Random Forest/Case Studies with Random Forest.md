# Case Studies with Random Forest
In this file, we will explore some case studies of using Random Forests in various applications.

1. **Random Forest for Classification: Titanic Dataset**
The Titanic dataset is a popular machine learning dataset that provides information about the passengers on board the Titanic, including whether they survived or not. In this case study, we will use Random Forest for classification to predict whether a passenger survived or not based on various features such as their age, sex, ticket class, and fare.

We will start by loading the dataset using the pandas library and performing some exploratory data analysis to get a better understanding of the data. Then we will preprocess the data by filling missing values and encoding categorical variables. Next, we will split the data into training and testing sets, and train a Random Forest classifier on the training data. We will tune the hyperparameters of the Random Forest using a randomized search, and evaluate the performance of the classifier on the testing data.

2. **Random Forest for Regression: California Housing Dataset**
The California Housing dataset contains information on the median house value for block groups in California, along with various other features such as the population, median income, and average number of rooms per dwelling.

In this case study, we can use Random Forest regression to predict median house values based on the other available features. The goal is to train a model that can accurately predict median house values for new block groups based on the available data.

We will start by loading the dataset using the scikit-learn library and performing some exploratory data analysis to get a better understanding of the data. Then we will preprocess the data by standardizing the features and splitting the data into training and testing sets. Next, we will train a Random Forest regressor on the training data. We will tune the hyperparameters of the Random Forest using a randomized search, and evaluate the performance of the regressor on the testing data.

3. **Random Forest for Feature Selection: Breast Cancer Dataset**
The Breast Cancer dataset is a popular machine learning dataset that provides information about the characteristics of breast cancer tumors, along with whether they are malignant or benign. In this case study, we will use Random Forest for feature selection to identify the most important features for predicting whether a tumor is malignant or benign.

We will start by loading the dataset using the scikit-learn library and performing some exploratory data analysis to get a better understanding of the data. Then we will preprocess the data by standardizing the features and splitting the data into training and testing sets. Next, we will train a Random Forest classifier on the training data, and use the feature importances to select the most important features. Finally, we will evaluate the performance of the classifier using only the selected features.


Here are some code snippets you can use to load the Titanic dataset and train a Random Forest model for classification:
### **Random Forest for Classification: Titanic Dataset**
```python
# Import necessary libraries
import pandas as pd
from sklearn.compose import ColumnTransformer
from sklearn.ensemble import RandomForestClassifier
from sklearn.impute import SimpleImputer
from sklearn.model_selection import train_test_split
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import OneHotEncoder

# Load the data
data = pd.read_csv('train.csv')

# Separate the target variable from the features
X = data.drop('Survived', axis=1)
y = data['Survived']

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Define the column transformer for the categorical variables
cat_transformer = Pipeline(steps=[
    ('imputer', SimpleImputer(strategy='most_frequent')),
    ('onehot', OneHotEncoder(handle_unknown='ignore'))])

# Define the column transformer for the numeric variables
num_transformer = SimpleImputer(strategy='mean')

# Use the column transformer to preprocess the data
preprocessor = ColumnTransformer(
    transformers=[
        ('cat', cat_transformer, ['Sex', 'Embarked']),
        ('num', num_transformer, ['Age', 'Fare'])
    ])

# Define the random forest classifier
rf = RandomForestClassifier()

# Create the pipeline
pipeline = Pipeline(steps=[('preprocessor', preprocessor),
                           ('classifier', rf)])

# Fit the pipeline to the training data
pipeline.fit(X_train, y_train)

# Make predictions on the test set
y_pred = pipeline.predict(X_test)

# Evaluate the performance of the model
score = pipeline.score(X_test, y_test)
print("Accuracy:", score)
```
**Accuracy: 0.7430167597765364** 

```python
from sklearn.metrics import confusion_matrix, classification_report
import matplotlib.pyplot as plt
import seaborn as sns

# Generate the confusion matrix
cm = confusion_matrix(y_test, y_pred)

# Visualize the confusion matrix as a heatmap
sns.heatmap(cm, annot=True, cmap='Blues', fmt='g')
plt.xlabel('Predicted')
plt.ylabel('Actual')
plt.title('Confusion Matrix')
plt.show()

# Generate the classification report
report = classification_report(y_test, y_pred)
print(report)

```
This code will create a heatmap of the confusion matrix and print out a classification report, which will give you a more detailed understanding of the model's performance.


![titanic görsel](https://user-images.githubusercontent.com/63750425/220707052-39801b50-495e-4c6f-b85c-f0f6e19068d6.png)


Datesset Link -----> https://www.kaggle.com/competitions/titanic/data?select=train.csv

This code snippet uses SimpleImputer with strategy='most_frequent' to impute missing values in the categorical variables (i.e., 'Sex' and 'Embarked') and SimpleImputer with strategy='mean' to impute missing values in the numeric variables (i.e., 'Age' and 'Fare'). It also uses OneHotEncoder to encode the categorical variables and handle unknown categories, and ColumnTransformer to apply the transformations to the appropriate columns. Finally, it fits a random forest classifier to the preprocessed data using a pipeline.


### **Random Forest for Regression: California Housing Dataset**
```python
from sklearn.datasets import fetch_california_housing
from sklearn.ensemble import RandomForestRegressor
from sklearn.model_selection import train_test_split

# Load the Boston Housing dataset
housing = fetch_california_housing()
X, y = housing.data, housing.target

# Split the data into training and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create a random forest regression model
rf = RandomForestRegressor(n_estimators=100, random_state=42)

# Fit the model to the training data
rf.fit(X_train, y_train)

# Evaluate the model on the test data
print(f"Test R^2 score: {rf.score(X_test, y_test):.3f}")

```
**Test R^2 score: 0.805**

The fetch_california_housing function is used to load the California Housing dataset.
The input features (X) and target variable (y) are assigned from the dataset.
The train_test_split function is used to split the data into a training set and a test set.
A RandomForestRegressor object is created with 100 trees and a random state of 42.
The fit method is called on the random forest object to train the model on the training data.
The score method is used to evaluate the model on the test data and returns the R^2 score, which is a measure of how well the model is able to fit the data.
Keep in mind that this is just a basic example, and there are many ways to customize a random forest regression model, including changing hyperparameters, optimizing features, and handling missing or categorical data.

```python
import matplotlib.pyplot as plt

# Make predictions on the test set
y_pred = rf.predict(X_test)

# Create a scatter plot of actual vs predicted values
plt.scatter(y_test, y_pred, alpha=0.5)
plt.xlabel("Actual Values")
plt.ylabel("Predicted Values")
plt.title("Random Forest Regression: California Housing Dataset")
plt.show()
```
![california housing](https://user-images.githubusercontent.com/63750425/220707090-b2b3f8a3-b997-4376-9989-e649e31527e5.png)



This code creates a scatter plot of the actual target values versus the predicted target values for the test set, using an alpha of 0.5 to make overlapping points more visible. The x-axis is labeled "Actual Values", the y-axis is labeled "Predicted Values", and the title of the plot is "Random Forest Regression: California Housing Dataset".


### **Random Forest for Feature Selection: Breast Cancer Dataset**
```python
from sklearn.datasets import load_breast_cancer
from sklearn.ensemble import RandomForestClassifier
from sklearn.feature_selection import SelectFromModel
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

# Load the breast cancer dataset
data = load_breast_cancer()
X, y = data.data, data.target

# Split the data into training and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create a random forest classifier model
rf = RandomForestClassifier(n_estimators=100, random_state=42)

# Train the model
rf.fit(X_train, y_train)

# Use the model to select features
selector = SelectFromModel(rf, prefit=True)
X_train_new = selector.transform(X_train)
X_test_new = selector.transform(X_test)

# Train a new model with the selected features
rf_new = RandomForestClassifier(n_estimators=100, random_state=42)
rf_new.fit(X_train_new, y_train)

# Evaluate the model on the test data
y_pred = rf_new.predict(X_test_new)
acc = accuracy_score(y_test, y_pred)
print(f"Test accuracy: {acc:.3f}")
```

** Test accuracy: 0.956** 

In this example, we load the breast cancer dataset, split it into training and test sets, and create a random forest classifier model. We then use the SelectFromModel class to select the most important features from the data based on the feature importances estimated by the random forest. Finally, we train a new random forest classifier using only the selected features and evaluate its performance on the test data.

```python
import matplotlib.pyplot as plt
from sklearn.datasets import load_breast_cancer

# Create a random forest classification model
rf = RandomForestClassifier(n_estimators=100, random_state=42)

# Fit the model to the breast cancer data
rf.fit(X_train, y_train)
cancer = load_breast_cancer()
# Get feature importances
importances = rf.feature_importances_
features = cancer.feature_names

# Sort feature importances in descending order
indices = importances.argsort()[::-1]

# Plot the feature importances
plt.figure()
plt.title("Breast Cancer Feature Importances")
plt.bar(range(X_train.shape[1]), importances[indices])
plt.xticks(range(X_train.shape[1]), features[indices], rotation=90)
plt.show()
```

This will create a bar plot showing the feature importances, with the most important features at the top. 
![breast cancer](https://user-images.githubusercontent.com/63750425/220707146-7f7b953e-d331-45fc-82ac-8507b4df89ca.png)
