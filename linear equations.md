### 1.2 - Solving Systems of Linear Equations using Matrices****
	A = np.array([
	        [4, -3, 1],
	        [2, 1, 3],
	        [-1, 2, -5]
	    ], dtype=np.dtype(float))
	
	b = np.array([-10, 0, 17], dtype=np.dtype(float))
	print("Matrix A:")`
	print(A)
	print("\nArray b:")
	print(b)
Return:
		Matrix A: [[ 4. -3. 1.] [ 2. 1. 3.] [-1. 2. -5.]] 
		Array b: [-10. 0. 17.]



Check the dimensions of A and b using <mark style="background: #ABF7F7A6;">`shape()`</mark>
	print(f"Shape of A: {np.shape(A)}")
	print(f"Shape of b: {np.shape(b)}")

`np.linalg.solve(A, b)` function to find the solution of the system (1). The result will be saved in the 1-D array x. The elements will correspond to the values of x1, x2 and x3:

<mark style="background: #ABF7F7A6;">x = np.linalg.solve(A, b)</mark>
print(f"Solution: {x}")
Solution: [ 1.  4. -2.]

### Evaluating the Determinant of a Matrix

A linear system containing three equations with three unknown variables will have one solution if and only if the matrix A has a non-zero determinant.

Let's calculate the determinant using <mark style="background: #FFF3A3A6;">`np.linalg.det(A)`</mark> function:
	d = np.linalg.det(A)
	print(f"Determinant of matrix A: {d:.2f}")

Determinant of matrix A: -60.00

