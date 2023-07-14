
The [[Perceptron]] is this single neuron operation 
![[Pasted image 20230711161647.png]]
Multiple inuts are not thought of points in a sequence. we still do not have this notion of temporal notion of time.

![[Pasted image 20230711161740.png]]



## Feed forward networks revistited

Imagine to make a copy a that handle the time steps in parralel or again and again. All these models are copies of eachother
![[Pasted image 20230711162048.png]]
 
A predicted output can later depend on the previous inputs
![[Pasted image 20230711162145.png]]

What if we link the computation and the information  by a reccurance relation and that something about what the network is computing  at a particular time is pased on at a particular time and is is passed on in h.


What this means that it's predictions and observations are not only based on the input data X, but also H which captures this notion of memory that is passed over time.

Y = f(x,h)
We have this temporal input X and our memory

![[Pasted image 20230711170154.png]]


This is the idea that is behind [[Recurrent Nural network]]
