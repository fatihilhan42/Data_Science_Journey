1. Resampling Techniques:

Oversampling:

```python
from imblearn.over_sampling import RandomOverSampler

ros = RandomOverSampler(random_state=42)
X_resampled, y_resampled = ros.fit_resample(X, y)

```

```python
from imblearn.under_sampling import RandomUnderSampler

rus = RandomUnderSampler(random_state=42)
X_resampled, y_resampled = rus.fit_resample(X, y)

```

```python
from imblearn.over_sampling import SMOTE

smote = SMOTE(random_state=42)
X_resampled, y_resampled = smote.fit_resample(X, y)

```

Class Weighting:

```python
from sklearn.svm import SVC

svm = SVC(class_weight='balanced')
svm.fit(X, y)
```

Ensemble Methods:

```python
from imblearn.ensemble import BalancedRandomForestClassifier

brf = BalancedRandomForestClassifier(random_state=42)
brf.fit(X, y)

```

Evaluation Metrics:

```python
from sklearn.metrics import classification_report

y_pred = model.predict(X_test)
print(classification_report(y_test, y_pred))

```

These are just a few examples of techniques that can be used to handle imbalanced datasets. Choose the appropriate technique based on your dataset and problem at hand. Remember to evaluate the performance of your model using appropriate evaluation metrics that account for class imbalance.