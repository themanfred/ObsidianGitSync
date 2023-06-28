![[Pasted image 20230408121506.png]]

### Keras
Here we use keras (a module inside of TensorFlow) to grab our datasets and read them into a pandas dataframe![[Pasted image 20230408121535.png]]
![[Pasted image 20230408121633.png]]

### Building the Model

And now we are ready to choose a model. For classification tasks there are variety of different estimators/models that we can pick from. Some options are listed below.

-   `DNNClassifier` (Deep Neural Network)
-   LinearClassifier: Dose classification rather than give a numeric value like a linear regression.`

![[Pasted image 20230408122859.png]]

What we've just done is created a deep neural network that has two hidden layers. These layers have 30 and 10 neurons respectively. This is the number of neurons the TensorFlow official tutorial uses so we'll stick with it. 
<mark style="background: #ADCCFFA6;">However, it is worth mentioning that the number of hidden [[neurons]] is an arbitrary number and many experiments and tests are usually done to determine the best choice for these values.</mark>

