Here is an example of using Naive Bayes for text classification using the **MultinomialNB** implementation from scikit-learn:

```python
from sklearn.datasets import fetch_20newsgroups
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.naive_bayes import MultinomialNB
from sklearn.pipeline import Pipeline
from sklearn.metrics import accuracy_score, classification_report

# Load the 20 newsgroups dataset
newsgroups_train = fetch_20newsgroups(subset='train')
newsgroups_test = fetch_20newsgroups(subset='test')

# Define a pipeline to vectorize the text data and train a Naive Bayes classifier
pipeline = Pipeline([
    ('vectorizer', CountVectorizer()),
    ('classifier', MultinomialNB())
])

# Train the classifier on the training data
pipeline.fit(newsgroups_train.data, newsgroups_train.target)

# Predict the labels of the test data
predicted = pipeline.predict(newsgroups_test.data)

# Evaluate the performance of the classifier
print(f"Accuracy score: {accuracy_score(newsgroups_test.target, predicted)}")
print(classification_report(newsgroups_test.target, predicted, target_names=newsgroups_test.target_names))

```

**Accuracy score: 0.7728359001593202
                          precision    recall  f1-score   support

             alt.atheism       0.79      0.77      0.78       319
           comp.graphics       0.67      0.74      0.70       389
           
    comp.os.ms-windows.misc       0.20      0.00      0.01       394
 
    comp.sys.ibm.pc.hardware       0.56      0.77      0.65       392

    comp.sys.mac.hardware       0.84      0.75      0.79       385
   
          comp.windows.x       0.65      0.84      0.73       395
          
            misc.forsale       0.93      0.65      0.77       390
            
               rec.autos       0.87      0.91      0.89       396
               
         rec.motorcycles       0.96      0.92      0.94       398
         
      rec.sport.baseball       0.96      0.87      0.91       397
      
        rec.sport.hockey       0.93      0.96      0.95       399
        
               sci.crypt       0.67      0.95      0.78       396
               
         sci.electronics       0.79      0.66      0.72       393
         
                 sci.med       0.87      0.82      0.85       396
                 
               sci.space       0.83      0.89      0.86       394
               
    soc.religion.christian      0.70      0.96      0.81       398
  
      talk.politics.guns       0.69      0.91      0.79       364
      
    talk.politics.mideast      0.85      0.94      0.89       376
   
      talk.politics.misc       0.58      0.63      0.60       310
      talk.religion.misc       0.89      0.33      0.49       251
      
                accuracy                           0.77      7532
               macro avg       0.76      0.76      0.75      7532
            weighted avg       0.76      0.77      0.75      7532**

In this example, we first load the **20 newsgroups** dataset, which is a collection of newsgroup posts partitioned into 20 different categories. We then define a pipeline that uses the **CountVectorizer** to convert the text data into a bag-of-words representation and trains a **MultinomialNB** classifier. We fit the pipeline on the training data and use it to predict the labels of the test data. Finally, we evaluate the performance of the classifier using accuracy and a classification report.

Note that the **MultinomialNB** implementation is commonly used for text classification tasks, but scikit-learn also provides other Naive Bayes implementations such as **GaussianNB** for continuous data and **BernoulliNB** for binary data.

```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.naive_bayes import GaussianNB
from sklearn.metrics import accuracy_score

# Load the Iris dataset
iris = load_iris()

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(iris.data, iris.target, test_size=0.2, random_state=42)

# Train the Naive Bayes classifier
clf = GaussianNB()
clf.fit(X_train, y_train)

# Predict the test set labels
y_pred = clf.predict(X_test)

# Calculate the accuracy of the classifier
accuracy = accuracy_score(y_test, y_pred)
print("Accuracy:", accuracy)
```
**Accuracy: 1.0**

In this example, we load the Iris dataset, split it into training and testing sets, train a Gaussian Naive Bayes classifier, predict the labels of the test set, and calculate the accuracy of the classifier. The Gaussian Naive Bayes classifier assumes that the features are normally distributed.
