Vectorization is basically the art of getting rid of explicit for loops in your code.![[Pasted image 20230816162018.png]]#whenever possible, avoid explicit for loops



u = Av

ui = Sum(j)(A(ij))(v(j))
u = np.zeros(n,1)
for i ..
for j ..
u[i] += A[i][j]* v[j]

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

