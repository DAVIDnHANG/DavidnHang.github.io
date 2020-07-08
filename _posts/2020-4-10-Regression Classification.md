---
layout: 10/1/2019 post
title: Regression Classification
image: 
---
Here are the columns of today dataset. 
```
Index(['bathrooms', 'bedrooms', 'created', 'description', 'display_address',
       'latitude', 'longitude', 'price', 'street_address', 'interest_level',
       'elevator', 'cats_allowed', 'hardwood_floors', 'dogs_allowed',
       'doorman', 'dishwasher', 'no_fee', 'laundry_in_building',
       'fitness_center', 'pre-war', 'laundry_in_unit', 'roof_deck',
       'outdoor_space', 'dining_room', 'high_speed_internet', 'balcony',
       'swimming_pool', 'new_construction', 'terrace', 'exclusive', 'loft',
       'garden_patio', 'wheelchair_access', 'common_outdoor_space'],
      dtype='object')
``` 
  Mean of what I am looking at 
Given the price of apartments right now, I want to know the best predictor for price with no other influence. 
So let examine price for May-April, then look at price again for June
``` 
from sklearn.metrics import mean_absolute_error
```
#Since we are looking at y, we want price to be in the y-axis.
```
target = 'price'
y_train = train_Date_ap_may[target]
y_test = test_Date_June[target]
```
get the mean of the training data then get the Since this is the population mean we use N, if this is SAMPLE, we use n-2
```
y_pred = [y_train.mean()] * len(y_train)
mae_train = mean_absolute_error(y_train, y_pred)

y_predtest = [y_train.mean()] * len(y_test)
mae_test = mean_absolute_error(y_test, y_predtest)

print("MAE for Train. In April-May, The price is about", mae_train, "more" )
print("MAE for test. in June, The price is about", mae_test, "more")
```
results are the following:
```
MAE for Train. In April-May, The price is about 1202.912286394699 more
MAE for test. in June, The price is about 1197.7032731340475 more
```
```
MAE for Train. In April-May, The price is about 1202.912286394699 more
MAE for test. in June, The price is about 1197.7032731340475 more
do the 5 steps to of linear regression on python.
```
The next steps are
1. instanteous linear regression
2. assign features and target
3. fit the model

1. Engineer at least two new features. 
 * high_speed_internet 
 * common_outdoor_space      
```
from sklearn.linear_model import LinearRegression
```
2. instantaneous the model
```
model = LinearRegression()
```
3. train, and features (train on the dataframe of April-May date) 
* split into two, train data and target data
```
features = ['high_speed_internet', 'bathrooms', 'bedrooms']
X_train = train_Date_ap_may[features]
X_test = test_Date_June[features]
print(f'The features will be,', features)
```
4. fit with at least two features
```
model.fit(X_train, y_train)
y_train_pred = model.predict(X_train)
train_mae = mean_absolute_error(y_train, y_train_pred)
print(train_mae)
```
5. now test
```
y_test_model = model.predict(X_test)
test_mae = mean_absolute_error(y_test, y_test_model )
print(test_mae)
The features will be, ['high_speed_internet', 'bathrooms', 'bedrooms']
817.840525712477
824.9354844292876
MAE is about 817 dollar off for training, and MAE 824 dollar off for test.
```
