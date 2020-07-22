---
layout: post
title: Linear Regression
---

Linear Regression

* f</sub>(x)</sub> = b<sub>0</sub> + b<sub>1</sub>x<sub>1</sub> + ... + b<sub>n</sub>x<sub>n</sub>
* such that b<sub>0</sub>, ..., b<sub>n</sub> are coefficients, and X<sub>1</sub>, ..., X<sub>n</sub> are features.

Features also mean independent variable, explanatory variable, regressor, covariate. Coefficients are the values that multiply the predictor values. b<sub>0</sub> means the Y-intercept coefficient. The coefficients influence the features by increasing or decreasing the corresponding 1, ... n features. <p>

If there exist many samples that have many features, we can predict a group of sample targets using a linear regression in Python.
We can put the n_sample and n_features into a matrix shape, then we can predict the features of the y_sample using the Linear Regression model.

There are 5 steps to do a linear regression on Python with Scikit-learn.
1. import the appropriate estimator class which are Multiple Regression, Ridge Regression, Logistic Regression.
  * Multiply Regression models a value based on multiple variables.
  * Ridge Regression are techniques to reduce model complexity.
  * Logistic Regression is used for category data.
2. instantaneous a model.
  * LinearRegressionModel = LinearRegression()
  * LogisticRegressionModel = LogisticRegression()
  * RidgeRegressionModel = Ridge()
  * selector = SelectKBest()
3. create the feature, and target variable for linear regression.
 
    the direct way is to put the columns of interested in a matrix then assign them to a x_train variable, while we have
the variable we are predicting to be assigned to y_train variable. There is also some unique ways to create features such as one-hot encoding, features engineering, high cardinality, and selectKBest
  * one-hot encoding is transforming categories into bits.
  * feature engineering is creating features by combine multiple features.
  * high cardinality refers to numbers that are uncommon or uniques, low cardinality refers to low uniques.
  * let the program choose the best correlate features by using selector = SelectKBest()
4. make the pred.
```
 model.fit(X_train, y_train)
 y_pred = model.predict(x_test)
```
if we use selector
```
 X_train_selected = selector.fit_transform(X_train, y_train)
 X_test_selected = selector.transform(X_test)

 model = LinearRegression()
 model.fit(X_train_selected, y_train)
 y_pred = model.predict(X_test_selected)
```

finally print the score
```
mean_absolute_error(y_test, y_pred)
```

```
