### A **tensor** is a generalization of vectors with matrices to potentially higher dimensions. 

Tensorflow represents tensors an n-dimensional arrays of datatypes.

Each tensor represents  a partially defined computation that will eventually produce a value.

What type of information is stored in the tensor.

Scalar value means one value.

### Rank/degree of tensors
These terms simply mean the number of dimesnions involved in the tensor.

You determine the rank of a tensor  with the deepest rank of nested lists/arrays.
Second one is a  rank two tensor = matrix
[]![[Pasted image 20230404100500.png]]
To determine a tensor 
 
tf.rank(variable)
![[Pasted image 20230404100601.png]]

### Shape of a Tensor

`THe shape of a tensor is the amount of elements that exist in each dimension.`
![[Pasted image 20230404100844.png]]
![[Pasted image 20230404100915.png]]

### Changing Shape
There are often many shapes that have the same number of elements, making it convinient to be able to change the shape of a tensor.

The amount of elements of a tensor is the product of all the sizes of all its shapes.

![[Pasted image 20230404101223.png]]
What I tod the model is that I want a tensor that has only ones, two arrays, and three elements per array

![[Pasted image 20230404101345.png]]

In the second tensor we reshaped tensor 1  have two lists, inside we have three lists and inside we have 1 element.

The -1 tells the tensor to calculate the size of the dimension in that place
 - This will reshape the tensor to [3,2] 3*2 =6

So  long  as it is a valid shape and when we multiplily all the numbers here to the one we are trying reshape it is fine.


### Types of Tensors
- **Variable** : is a variable, but in tensor form.
- **Constant** : Whatever we defined here will not change.


### Evaluating Tensors 
Since tensors rep. partially complete computations we will sometimes need to run what's called a **session to evaluate the tensor**
![[Pasted image 20230404102325.png]]


### .head()

![[Pasted image 20230407155722.png]]

### .describe() 
![[Pasted image 20230407160405.png]]
  print(vocabulary)
### Categorical data

Any data that is not <mark style="background: #FFF3A3A6;">numerical</mark> m

###  The Training Process

So, we are almost done preparing our dataset and I feel as though it's a good time to explain how our model is trained. Specifically, how input data is fed to our model.

For this specific model data is going to be streamed into it in small batches of 32. This means we will not feed the entire dataset to our model at once, but simply small batches of entries. We will feed these batches to our model multiple times according to the number of **epochs**.

### Epoch
An **<mark style="background: #ADCCFFA6;">epoch</mark>** is simply one stream of our entire dataset. The number of epochs<mark style="background: #ABF7F7A6;"> we define is the amount of times our model will see the entire dataset. </mark>We use multiple epochs in hope that after seeing the same data multiple times the model will better determine how to estimate it.


We want to avoid overfeeding the model because then it might memorize the data given and be really good for those data points, but for new data given it is really not as good.

Ex. If we have 10 ephocs, our model will see the same dataset 10 times.

Since we need to feed our data in batches and multiple times, we need to create something called an<mark style="background: #FF5582A6;"> input function.</mark> 

### Input Function
The input function simply defines how our dataset will be converted into batches at each epoch.

The TensorFlow model we are going to use requires that the data we pass it comes in as a `tf.data.Dataset` object. This means we must create a _input function_ that can convert our current pandas dataframe into that object.



### Estimators 
All core algorithms use estimators which are justbasic imlementations of alg. of tenserflow.


### Training the Model 
Training the model is as easy as passing the input functions that we created earlier.


## Classification

 Where regression was used to predict a numeric value, classification is used to seperate data points into classes of different labels. 
