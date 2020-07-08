---
layout: post
title: Electronic Price by Weight
---
![image](/img/KnockOutOneHUndred.PNG)
 
 Let knock out all weight that more than 100 pounds. More than 100 pounds means that
those machines are for business uses, or a set of electronic that comes together.

![image](/img/WeightXPrice.PNG)
 
 Working on this data set should be cleaner. 
  
  
![image](/img/Merchant.PNG)
  
 The column with the merchant has too many unique merchants. Also Bestbuy, bhphotovideo, walmart, and beach Camera dominate this columns.
 So let's keep those five and rename all other merchant to others.
  
 Also, there are three dates columns on this dataset. Let combined two of the column which are "first stocked" and "last seemed" to create an engineer features, "how old." Also let remove the third date column.
  
 We will remove 
   * ID
   * asins, keys, manufacturer, manufacturerNumber These are different ways of saying the brand.
   * upc - barcode doesn't help us.

Finally, we will train, validate, test our data set on these features: available, condition, sale merchant, shipping method and weight.
Also two new engineer features, HowOld, and brand, and Merchant. We will use One Hot Encoding because the cardinality of all the columns is less than 5, and XGBregressor, to fit training data set, and predict the model.



![image](/img/accuracy.PNG)

As you can see in this pdp plot, although the prediction always surrounded the true value, it should be 100-200 dollar off. which is quite expensive
for this type of model.

![image](/img/pdp plot.PNG)


Let describe the PDP for feature "weight plot". Each line represents an observation.They all have the same shape. From 5 pounds, I
can suspect small electronic device. Depending on the number of rams, sticks I can foresee it being around 400-600 dollars.
Then as we go 20-30 pounds, probably price of one television, or computer monitor. Then 30+, we get into the bigger television,
then with association with the brand name, sales, we get the difference in pricing.

![image](/img/PartialDependencePlotForWeightXPrice.PNG)

**Prediction**
During Monday night football game on Oct 21, 2019 Patriot vs Jets, I was seeing a ghost too.
If there was a way to input some numbers into a program which will predict me a price.
```
  'BlackBox(54,0,0,1,0,0,0,0,0,1,0,0,0,0,0,1,0,0,1,0,0,0,0,0,0,1,0,0,0''')'
```
![image](/img/assets.PNG)

The blackbox give us a price of 1,652.13.  The electronic equipment is 
  * This function is just saying, this product is 54 lbs, fresh off the truck, at walmart who will ship it for free, and has been on the shelf for less than 6 month and a round error of 200 dollar. 
  * You get a 75 inch, 4k ultra hd, hdr song tv.
  
*A little to expensive so let go a lower*
 ```  
    'BlackBox(32,0,0,1,0,0,0,1,0,0,0,0,0,0,0,1,0,0,1,0,0,0,0,0,0,0,1,0,0)  ''')'
```   
![image](/img/weightThirtyTwolb.PNG)
    How about a television that weighs around 32 pounds, unopened box, sold at Amazon.com will
  be shipped to your house with free shipping over 100 bucks, and has been sitting on the shelf between 7-12 months.
  You get a 55 inch, LG ThinQ, with fresh electronic chemicals smell when you opened the box for 704.16 dollars.
```  
  'BlackBox(1,0,0,0,0,1,0,1,0,0,0,0,0,0,0,1,0,0,1,0,0,0,0,0,0,0,1,0,0)'
```
![image](/img/ShapSevenNew.PNG)
![image](/img/ShapSevenPound.PNG)

something around 200 dollar that weights around 1-6 pounds is a nintendo switch
    
    

