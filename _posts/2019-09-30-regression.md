---
layout: post
title: Flake it till you make it
subtitle: Regression
bigimg: 
tags: regression
---
  
  
  A little about Linear Regression. Let f(x) = b_0+b_1x_1 + ... + b_nX_n such that B_0, b_n are the coefficient and X_1 is what the features are. B_0 is when all the feature are zero after whatever features we want. F(x) is the target.
 
 
 There are 5 steps to do a linear regression on Python with SCikit-learn.
 1) import the approprite estimastor class from scikit-learn.
 2) Instanteous a model. In this case we will do linear regression. 
 model = LinearRegression()
 3) create the feature, and target variable for linear regression.
 FOr this example, we will use a dataset from 
csv('../data/apartments/renthop-nyc.csv'). a file that has rent of apartment with bedrooms, bathroom, long & latitude with other etc hardwoord, floor, patio. 
Let do number of bathroom as feature and rent price as target.
X_test.predict(X_test)
y_pred = model.predict(X_test)
y_pred is the guesstimation of price for whatever price you enter in.