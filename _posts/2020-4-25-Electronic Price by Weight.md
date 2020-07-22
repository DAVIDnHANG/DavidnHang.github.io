---
layout: post
title: Electronic Price by Weight
---
![image](/img/KnockOutOneHUndred.PNG)

I removed the weights that are more than 100 pounds because those machines are used for business purpose. I want
to target personal use electronics. 


![image](/img/WeightXPrice.PNG)


![image](/img/Merchant.PNG)

The merchant column has many unique merchants. Also Bestbuy, bhphotovideo, Walmart, and Beach Camera dominate this columns.
I will not rename those five columns, but rename the other merchant to others.

I will use this process called engineer features to create "How Old" from both "First Stocked" and "Last Seemed."

I will remove these three columns:
  * ID
  * asins, keys, manufacturer, manufacturerNumber These are different ways of saying the brand.
  * upc - barcode doesn't help us.

Finally, we will train, validate, test our data set on these features: available, condition, sale merchant, shipping method and weight.

We will use One Hot Encoding because the cardinality of all the columns is less than 5, and XGBregressor, to fit the training data set, and predict the model.



![image](/img/accuracy.PNG)

As you can see in this pdp plot, although the prediction always surrounded the true value, it should be 100-200 dollar off.

![image](/img/pdp plot.PNG)

The price based on weight is not a good indicator to predict electronic prices. A 5 pounds electronic can be 400-600 dollars. Then electronics weighing 20-30 pounds can be priced between 100-1000 because they are television, computer monitors. Then electronic over 30 pounds we can get between bigger televisions, associated with the brand name, sales,we get different pricing.



![image](/img/PartialDependencePlotForWeightXPrice.PNG)

**Prediction**

```
 'BlackBox(54,0,0,1,0,0,0,0,0,1,0,0,0,0,0,1,0,0,1,0,0,0,0,0,0,1,0,0,0''')'
```
![image](/img/assets.PNG)

The blackbox give us a price of 1,652.13.  The electronic equipment is
 This product is 54 lbs, fresh off the truck, at Walmart who will ship it for free, and has been on the shelf for less than 6 month and a round error of 200 dollar. When everything is accounted for it is priced at 1,652.15 dollars for a 75 inch, 4k ultra hd, hdr song tv.

*A little too expensive so let go a lower*
``` 
   'BlackBox(32,0,0,1,0,0,0,1,0,0,0,0,0,0,0,1,0,0,1,0,0,0,0,0,0,0,1,0,0)  ''')'
```  
![image](/img/weightThirtyTwolb.PNG)
   How about a television that weighs around 32 pounds, unopened box, sold at Amazon.com will
 be shipped to your house with free shipping over 100 bucks, and has been sitting on the shelf between 7-12 months.
 You get a 55 inch, LG ThinQ, with fresh electronic chemicals smell when you open the box for 704.16 dollars.
``` 
 'BlackBox(1,0,0,0,0,1,0,1,0,0,0,0,0,0,0,1,0,0,1,0,0,0,0,0,0,0,1,0,0)'
```
![image](/img/ShapSevenNew.PNG)
![image](/img/ShapSevenPound.PNG)

something around 200 dollar that weighs around 1-6 pounds is a nintendo switch


