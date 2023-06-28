NumPy allows you to quickly perform elementwise addition, substraction, multiplication and division for both 1-D and multidimensional arrays. The operations are performed using the math symbol for each '+', '-' and '*'. Recall that addition of Python lists works completely differently as it would append the lists, thus making a longer list, in addition, subtraction and multiplication of Python lists do not work. 

Rather than using lists and than iterating using loops this is much faster computationally

arr_1 = np.array([2, 4, 6])
arr_2 = np.array([1, 3, 5])

#### Adding two 1-D arrays
addition = arr_1 + arr_2
print(addition)

#### Subtracting two 1-D arrays
subtraction = arr_1 - arr_2
print(subtraction)

### Multiplying two 1-D arrays elementwise
multiplication = arr_1 * arr_2
print(multiplication)


Output:

[ 3  7 11]
[1 1 1]
[ 2 12 30]

The alternative would be a loop lke this

for i in arr_1:
	for j in arr_2:
		mathOp = 
print(mathOp)

## Multiplying vector with a scalar 

This concept is called **broadcasting**, which allows you to perform operations specifically on arrays of different shapes. 

vector = np.array([1, 2])
vector * 1.6
![[Pasted image 20230503213956.png]]
Output
array([1.6, 3.2])