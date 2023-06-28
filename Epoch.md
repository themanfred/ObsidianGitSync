
An **<mark style="background: #ADCCFFA6;">epoch</mark>** is simply one stream of our entire dataset. The number of epochs<mark style="background: #ABF7F7A6;"> we define is the amount of times our model will see the entire dataset. </mark>We use multiple epochs in hope that after seeing the same data multiple times the model will better determine how to estimate it.


We want to avoid overfeeding the model because then it might memorize the data given and be really good for those data points, but for new data given it is really not as good.

Ex. If we have 10 ephocs, our model will see the same dataset 10 times.

Since we need to feed our data in batches and multiple times, we need to create something called an<mark style="background: #FF5582A6;"> input function.</mark> 