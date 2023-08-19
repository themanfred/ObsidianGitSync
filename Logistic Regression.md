It is an algorithm for [[Binary classification]].

Want to classify something. Therefore 0 if it is not, 1 if it is.
![[Pasted image 20230814112522.png]]


If this image is a 64 by 64 image, the total dimension of this vector x will be 64 by 64 by 3 because that's the total numbers we have in all of these matrixes. 

![[Pasted image 20230814113015.png]]
Which in this case, turns out to be 12,288, that's what you get if you multiply all those numbers. And so we're going to use nx=12288 to represent the dimension of the input features x.

# Notation 
	
A single training example is represented by a pair (x,y)

A single training example is represented by a pair (x,y)
x is an nx dimmenal feature vector and y s {0,1}
![[Pasted image 20230814113155.png]]

m training example
![[Pasted image 20230814113231.png]]
mtrain && mtest = # test examples


Implementing NN with Columns for x, will make it much easier.
![[Pasted image 20230814113402.png]]

X in this case is an nx * m dimentional matrix
X*shape is (nx,m)
![[Pasted image 20230814113435.png]]



Y in this case is
![[Pasted image 20230814113536.png]]



Given x, want y=P(y=1 | x) where I want to identify if it is a cat (for this ex)
y=P(y=1 | x)  means that what is the probability of y=1 given the feature index x.

x is an nx dimentional vectior


Parameters wnx dimentional vectior, b is all real values.

Output y = wT*x+b

this is not a good alg. for this case since we want y=P(y=1 | x)  to be 0<=y<=1

So we apply a [[sigmoid function]]
y = s(wT*x+b)


![[Pasted image 20230814114119.png]]
When z is large it converges to ~1
When z is large negative it converges to ~0

There is also this notation
![[Pasted image 20230814114338.png]]

# Cost Function

![[Pasted image 20230814114451.png]]
Where we have a set number of m training examples and want as many predictions for <mark style="background: #FF5582A6;">y(i)</mark> =y. 

Note:
1. <mark style="background: #FF5582A6;">y(i)</mark> is y hat
2. The superscript i refers to the i-th example.
![[Pasted image 20230814114723.png]]

Loss (error) function:
L(<mark style="background: #FF5582A6;">y</mark>,y) = .5(<mark style="background: #FF5582A6;">y</mark>-y)^2
L(<mark style="background: #FF5582A6;">y</mark>,y) = -(y*log<mark style="background: #FF5582A6;">y</mark> +(1-y) * (log(1-<mark style="background: #FF5582A6;">y</mark>)))

If y =1 
L(<mark style="background: #FF5582A6;">y</mark>,y)  =  -ylog<mark style="background: #FF5582A6;">y</mark> want log<mark style="background: #FF5582A6;">y</mark> to be large -_> want <mark style="background: #FF5582A6;">y</mark> to be large

If y=0 
L(<mark style="background: #FF5582A6;">y</mark>,y)  =  -log<mark style="background: #FF5582A6;">1-y</mark> want log<mark style="background: #FF5582A6;">1-y</mark> to be large -_> want <mark style="background: #FF5582A6;">y</mark> to be small
![[Pasted image 20230814115630.png]]

The cost function measures how well you are doing on a single training set:

J(w,b)=1/m(sum(L(<mark style="background: #FF5582A6;">y</mark>,y))) = -1/m(sum((y*log<mark style="background: #FF5582A6;">y</mark> +(1-y) * (log(1-<mark style="background: #FF5582A6;">y</mark>))))
![[Pasted image 20230814140301.png]]
Logistic regression can be viewed as a very very small NN.

-----------

**The loss function computes the error for a single training example; the cost function is the average of the loss functions of the entire training set.** 

----------

# Gradient Descent

The loss functions how the yi measures to <mark style="background: #FF5582A6;">y</mark> , where we want to find 2, b that minimize J(w,b)

![[Pasted image 20230814140410.png]]

We want to find the local optima.

Where we initialize to some initial value usually at 0. Takes a step and starts going down.

Regarding m: Normalization
---
This 'm' represents the number of training examples or samples in your dataset. The reason for this division is to normalize the loss across the dataset, <mark style="background: #FFF3A3A6;">making the cost function independent of the dataset size</mark>. By doing this, you ensure that the learning process remains consistent regardless of whether you have a small or large dataset.

Think of it as a way to make your algorithm's performance measure consistent and comparable, regardless of the number of examples you're training on. This normalization helps prevent the algorithm from favoring datasets with larger or smaller sizes.

Repeat:
w:= w -a J(u)/du
a = alpha is the learning rate

--dw is the derivative or the chainrule derivative (tape)

![[Pasted image 20230814140800.png]]

Here the slope dJ(w)/dw is decreasing and it will move me to the local minimum over time.


w:= w -a J(w,b)/dw   -> <mark style="background: #FFB86CA6;">This will be dw in code</mark>

b:= b -a J(w,b)/db -> <mark style="background: #FFB86CA6;">This will be db in code</mark>

If J is a function of two or more variable we use the fancy d for the derivative in respect to the rate of change.

![[Pasted image 20230814141405.png]]


A look at [[Derivatives]]


# Computation Graph 

Let's say we have this equation:
J(a,b,c) = 3(a+b*c)

u = b*c
b=a+u
J = 3*v

![[Pasted image 20230814143634.png]]

If we want to optimize J or derrive in forward propagation in this case takes 3 steps

On the other hand,

One step of backward propagation on a computation graph yields derivative of final output variable.



Derivatives with a computation graph:

 We might find a final output variable. 
We try to compute these final variable with respect to some other variable.

![[Pasted image 20230814144921.png]]
<mark style="background: #FFF3A3A6;">In code the dFinalOutputVar/dvar : The derivative of a final output variable with respect to various intermediate quantities.</mark>



The most efficient way to do a derrivative is to follow right to left direction of the red arrows since computationally it is easier.

![[Pasted image 20230814145549.png]]

In this case da= 3, db =6 , dc = 9

# Logistic Regression Recap
![[Pasted image 20230814152157.png]] 


This rewritten would be ![[Pasted image 20230814152906.png]]
Where we get the losss function  of this logistic regression

## Logistic Regression Gradient Descent

Derivative of this loss with respect to a, using the chain rule
![[Pasted image 20230815151133.png]]
the simplified formula for the derivative of the losswith respect to z?
a - y.


# Gradient Descent on m examples

J(w,b) = 1/m (L)
a(i)= y(i) = s(z((i)))= s()wx(i)+b)

![[Pasted image 20230815162508.png]]


Let's intialize J=0 , dw= o ; dw2=0 ; db=0
for i=1 to m 
	z(i)=wx(i)+b
	a(i)=s(z(i))
	J += -(y(i)loga(i)+(1-y(i)) loga(1-a(i)))
	dz(i) = a(i) - y(i)
	dw(i) += x(i)dz(i)
	dw2 += x2dz
	db += dz(i)
J /=m
dw1 /= m
dw /2= m
db /= m
	
w1 := w1 - a*dw1
w2 := w2 - a*dw2
w3 := w3 - a*dw3


Same thing as writing 
u = np.dot(A,v)

![[Pasted image 20230819123357.png]]

Say you want to apply the exponential on evey element on the matrix/vector

u = np.zeros(n,1)
for i in range(n):
	u[i]= math.exp(v[i])


with numy 

import numy as np 
u = np.exp(v

np.log(v))
np.abs(v)
np.maximum(v,0)

![[Pasted image 20230819124938.png]]


Whenever I am tempted to write a for loop see if I can do something to do about it.

![[Pasted image 20230819124726.png]]


Here dwj where j is the value from 1...nx for the weights w.


To do this we get tid of dw and make dw a vector.

dw = np.zeros((n0x ,1)

replace the for loop for dw += x(i)dz(i)
![[Pasted image 20230819125233.png]]


# Vecotorizing Logistic Regression

X=
z(1) = wt*x(1) +b
a(1) = sigmoid_function(z(1))

z(2) = wt*x(2) +b
a(2) = sigmoid_function(z(2))
...
z(nx) = wt*x(nx) +b
a(nx) = sigmoid_function(z(nx))

Do this nx times.


(nx,m) Rnx*m dimensional matrix

Z = [z(1), z(2),...,z(m)]= wT *X + [b b, ,b  ] <- This b is a [1*m] vector
![[Pasted image 20230819130011.png]]

The [[numpy]] command wT *X + [b b, ,b  ]  is:
z = np.dot(w.T,x)+b 
where b is R, this is called broadcasting in [[Python]]

We then want to compute
A = [a(1 a(2) a(3) ... a(m)] = sigmoid_function(z(nx))

This is how you implement a vectorize implementation of the four propagation for all M training examples at the same time.


## # Vectorizing Logistic Regression's Gradient Output

dz(1) = a(1)- y(1)
dz(2) = a(2)- y(2) .. to m 
dz = [dz(i) dz(2) ... dz(m)]

A = [a(1) ... a(n)] Y = [ y(1) ... y(m)]
dz = A-Y = [a(1)*y(1) a(2)*y(2  a(1)*y(1)) ]

here we have
dw = 0 
dw += x(i)dz(i)
dw += x(i)dz(i)


![[Pasted image 20230819131231.png]]

Here we are trying to replace all the implementations:

z  = wT *x +b
 = np(dot(w.T, x)) +b

A = sigmoid_function(z)

dz = A-Y

![[Pasted image 20230819132532.png]]



## Broadcasting
![[Pasted image 20230819143322.png]]

How i would look like
![[Pasted image 20230819143532.png]]

![[Pasted image 20230819143610.png]]

General principle of broadcasting:
![[Pasted image 20230819143811.png]]


Don't use rank 1 arrays
![[Pasted image 20230819144638.png]]

