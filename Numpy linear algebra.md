[[NumPy]] linear algebra package provides quick and reliable way to solve the system of linear equations using function `np.linalg.solve(A, b)`. Here A is a matrix, each row of which represents one equation in the system and each column corresponds to the variable x1, x2. And b is a 1-D array of the free (right side) coefficients. More information about the `np.linalg.solve()` function can be found in [documentation](https://numpy.org/doc/stable/reference/generated/numpy.linalg.solve.html).


A = np.array([
        [-1, 3],
        [3, 2]
    ], dtype=np.dtype(float))
	b = np.array([7, 1]type=np.dtype(float))
	print("Matrix A:")
	print(A)
	print("\nArray b:")
	print(b)

	Prints: Matrix A: [[-1 3] [ 3 2]] Array b: [7 1]

Check the dimensions of $A$ and $b$ using the `shape` attribute (you can also use `np.shape()` as an alternative):

print(f"Shape of A: {A.shape}")

print(f"Shape of b: {b.shape}")

  
Shape of A: (2, 2) Shape of b: (2,)


### To solve it we simply use:
<mark style="background: #FF5582A6;">x = np.linalg.solve(A, b)</mark>
	print(f"Solution: {x}")

	Solution: [-1.  2.]
-----------

## Evaluating Determinant of a Matrix
Let's calculate the determinant using `NumPy` linear algebra package. You can do it with the `np.linalg.det(A)` function. More information about it can be found in [documentation](https://numpy.org/doc/stable/reference/generated/numpy.linalg.det.html).
In order to work, the matrix needs to be a square number. Or it will give the following error:
		`Last 2 dimensions of the array must be square
Otherwise:

<mark style="background: #FFF3A3A6;">d = np.linalg.det(A)</mark>
print(f"Determinant of matrix A: {d:.2f}")
	Determinant of matrix A: -11.00

---
### 2.2 - Preparation for the Implementation of Elimination Method in the Code

  
Representing the system in a matrix form as

![[Pasted image 20230522122721.png]]

you can apply the same operations to the rows of the matrix with Python code.

  

Unify matrix $A$ and array $b$ into one matrix using `np.hstack()` function. 

`Note that the shape of the originally defined array $b$ was $(2,)$, to stack it with the $(2, 2)$ matrix you need to use `.reshape((2, 1))` function:
![[Pasted image 20230522123009.png]]

Return a row 
print(A_system`[1])
<mark style="background: #CACFD9A6;">Returns 3 2 -2 1</mark>
Return a column or specific value
print(A_system`[1][0]) 
<mark style="background: #FFF3A3A6;">Returns 3</mark>