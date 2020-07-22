---
layout: 10/1/2019 post
title: Regression Classification
image:
---
There are 34 columns. 
```
      'bathrooms', 'bedrooms', 'created', 'description', 'display_address',
      'latitude', 'longitude', 'price', 'street_address', 'interest_level',
      'elevator', 'cats_allowed', 'hardwood_floors', 'dogs_allowed',
      'doorman', 'dishwasher', 'no_fee', 'laundry_in_building',
      'fitness_center', 'pre-war', 'laundry_in_unit', 'roof_deck',
      'outdoor_space', 'dining_room', 'high_speed_internet', 'balcony',
      'swimming_pool', 'new_construction', 'terrace', 'exclusive', 'loft',
      'garden_patio', 'wheelchair_access', 'common_outdoor_space'
```
One will estimate the price of the apartment in June using the data in May.  
```
from sklearn.metrics import mean_absolute_error
target = 'price'
y_train = train_Date_ap_may[target]
y_test = test_Date_June[target]
```
To determine the price in June, we use data from April-May. 
```
y_pred = [y_train.mean()] * len(y_train)
mae_train = mean_absolute_error(y_train, y_pred)

y_predtest = [y_train.mean()] * len(y_test)
mae_test = mean_absolute_error(y_test, y_predtest)
```

The price is around 1202.91 in April to May.
The price is around 1197.70 in June.

