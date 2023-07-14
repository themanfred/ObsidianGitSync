Applying the chain rule where we can decompose this derivative into two components 

![[Pasted image 20230710192421.png]]


If we wanted to measure w1
it would be:
![[Pasted image 20230710192703.png]]
Repeat for every step. 
In this case it could be added that dy/dw2 can also be included resulting in

dJ(W)/dw1 = dJ(W)/y* dy/dw2 * dw2/dz1 * dz1/w1

How much does a small change in these weights affect our loss if it increases or decreases and how can we use that to imporve


----
## Loss function can be difficult to optimize

Setting the learning rate can be really difficult to do.

![[Pasted image 20230710193304.png]]

**Too low**:
If we set the learning too low, we might not only converge too slowly and get stuck at a local minima, 

**Too High**
Large learning rates overshoot become unstable and diverge
![[Pasted image 20230710193547.png]]

 
Soooooo we need to create algorithms that make sure that the learning rates are no longer fixed.

- Can be made larger or smaller depending on:
	- How large gradient is
	- How fast learning is happening
	- Size of particular weights
