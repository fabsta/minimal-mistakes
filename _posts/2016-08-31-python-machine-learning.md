---
title: "Python Machine Learning Cheat Sheet"
description: "Python Machine Learning Cheat Sheet"
category: Programming
tags: [programming]
sidebar:
  nav: "new_side"
---
[source](https://www.analyticsvidhya.com/blog/2015/05/data-visualization-python/)

# Table of contents

* TOC
{:toc}


# Preparation

## split training data
```python
from sklearn.cross_validation import train_test_split
x_train,x_test, y_train, y_test = train_test_split(X, y, random_state = 1 )
```

(<a href="#top">Back to top</a>)
<hr>


## Linear regression

```python
from sklearn import datasets
-
from sklearn.linear_model import LinearRegression
-
lr.fit(boston.data, boston.target)
-
predictions = lr.predict(boston.data)
-
lr.coef_
zip(boston.feature_names, lr.coef_)
```

## Linear Regression (ridge)

## Logistic Regression

## Gradient Boosting


# Clustering

## KMeans

### Prepare Data
```python
from sklearn.datasets import make_blobs
```

### Plot initial clusters
```python
import matplotlib.pyplot as plt
f, ax = plt.subplots(figsize=(7.5, 7.5))
```

### Run KMeans
```python
from sklearn.cluster import KMeans
kmean.cluster_centers_ # print centers
```

## KKmeans (minibatch for large data)


## Probabilistic clustering with Gaussian Mixture Models


# Classification

## Decision tree

```python
from sklearn import datasets

from sklearn.tree import DecisionTreeClassifier
dt = DecisionTreeClassifier()

preds = dt.predict(X)
```

## Random Forest

```python
from sklearn import datasets

X, y = datasets.make_classification(1000)    #create the dataset with 1,000 samples

from sklearn.ensemble import RandomForestClassifier

print "Accuracy:\t", (y == rf.predict(X)).mean()
print "Total Correct:\t", (y == rf.predict(X)).sum()
```

### Feature importance

```python
rf = RandomForestClassifier(compute_importances=True)
```

### Tuning Random Forest

#### Confusing matrix

```python
import numpy as np

from sklearn.metrics import confusion_matrix
       rf.fit(X[training], y[training])
```

Look at confusion matrix

```python
import pandas as pd
```

#### Number of Estimators: Iterating through 1 - 20

```python
n_estimator_params = range(1, 20)
                                         
accuracy = lambda x: np.trace(x) / np.sum(x, dtype=float)
```

## Support Vector Machine

```python
from sklearn import datasets
from sklearn.svm import SVC
```

## Decision Tree Classifier

```python
from sklearn import datasets
		n_informative=3)
```




```python
from sklearn.ensemble import RandomForestClassifier
from sklearn.cross_validation import train_test_split
# Training a RF to get some metrics
X_train, X_val, y_train, y_val = train_test_split(train, train_outcome, test_size=0.1)
forest = RandomForestClassifier(n_estimators=250, n_jobs=2)
forest.fit(X_train, y_train)
y_pred_val = forest.predict(X_val)
from sklearn.metrics import classification_report, accuracy_score
print(classification_report(y_val, y_pred_val))
print(accuracy_score(y_val, y_pred_val))
# Training a RF with the complete training set
forest = RandomForestClassifier(n_estimators=500, n_jobs=2)
forest.fit(train, train_outcome)
y_pred = forest.predict_proba(test)
```

(<a href="#top">Back to top</a>)
<hr>



# Support Vector machine
```python
from sklearn.svm import SVC
model = SVC(kernel='linear')
model = model.fit(train_data[0:,2:], train_data[0:,0])
```

(<a href="#top">Back to top</a>)
<hr>