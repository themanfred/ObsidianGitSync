
![[Pasted image 20230406114419.png]]

![[Pasted image 20230406130140.png]]

Why learn DL and why now?

Hand engineered features are time consuming, brittle and not scalable in practice.

Can we learn the **underlying features** directly from data?

- Data is so much more prevasive than ever before and more data is available than ever before.
- This models are massively parallelizable
- Improved Techniques 
- New Models

![[Pasted image 20230710152709.png]]


Work with a single neuron- The [[Perceptron]]

We can start thinking how we can stack this layers.

How can we define and transform this inputs and closer to the value we want to predict.

![[Pasted image 20230710160331.png]]
 in this case z2 is taking the dot product adding a bias and then applying the non-linearity.

There is no extra complexity from perceptron to perceptron.
![[Pasted image 20230710160446.png]]


## Sequential models

Every layer will be fully connected to the next layer.


### #Question Then what is a Deep Neural Network?

A DNN is takes place where we stack different layers to create more hierarchical models and going deeper and deeper into the system.

![[Pasted image 20230710160722.png]]

#Example
Will I pass this class?

![[Pasted image 20230710160943.png]]

#Question Why does this NN think that it is not likely you pass the exam?
![[Pasted image 20230710161017.png]]

Here it looks like it will not pass the exam.
![[Pasted image 20230710161208.png]]

We need to train our model to understand how things work. So at the begining any input will not let it know if it is good or bad.


[[Cross entropy loss ]]

![[Pasted image 20230710162047.png]]


What we ultimately want to do over the course of entire data set we want to minimize all of the mistakes that a data makes
![[Pasted image 20230710161413.png]]


To get a yes or no or pass or fail.

On the otherhand we can have a [[mean squared error loss]]

---
## Training NN
### Loss optimization 
- We want to find the network weight that achieve the lowest loss.
![[Pasted image 20230710162702.png]]

ArgMin is **typically used to find the smallest possible values given constraints**.


We want to find the network weights that achieve the lowest loss.

We want to find the set of weights that on average give us the smallest lowest loss.
![[6S191_MIT_DeepLearning_L1.pdf]]

DL algorithm - [[Gradient Descent]]
