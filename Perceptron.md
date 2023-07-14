The structural building block of deep learning  NN![[Pasted image 20230710152945.png]]
On the left hand  - taking m set of inputs (x). How it works:
1. First is the dot product
2. Second the bias
3. Third is the non-linearity
![[Pasted image 20230710155700.png]]
The input is multiplied by the weight.

![[Pasted image 20230710153209.png]]

 A very common example that can be used is a [[sigmoid function]]
g()- In this case is the common activation function
![[Pasted image 20230710154810.png]]

For example in the sigmoid function It activates between 0 - 1. 
![[Pasted image 20230710154856.png]]

<mark style="background: #FF5582A6;">**The purpose of a nonlinear activation function is to intoduce non-linearities into the network.**</mark>

What if we wanted to build a neural network to distinguish green vs. red points.

![[Pasted image 20230710154956.png]]

Non linearities allow us to approximate compex functions.

------

To get the output of a preceptron .
1. First compute the multp.  inputs with the  weight  // which would be z
2. Add the result // still z
3. Compute the non-linearity  //g(z)

![[Pasted image 20230710155517.png]]
The component inside the 2D we can plot it inside a decision boundary.
![[Pasted image 20230710155536.png]]
<mark style="background: #FFB86CA6;">There is a directionality component. We actually can expect 
based on where is the point in the graph</mark>. To determine if it is negative or positive for example

--------
g()- is our activation file
z- dotproduct * **bias** 
![[Pasted image 20230710155815.png]]

## Multi- Output Perceptron 

Dense layer from scratch

![[Pasted image 20230710160240.png]]

