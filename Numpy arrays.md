Arrays are one of the core data structures of the NumPy library, essential for organizing your data. You can think of them as a grid of values, all of the same type. 

Python lists are limited in functions and take up more space and time to process than NumPy arrays.

<mark style="background: #ABF7F7A6;">[[NumPy]] provides an array object that is much faster and more compact than [[Python]] lists. </mark>

Through its extensive API integration, the library offers many built-in functions that make computing much easier with only a few lines of code. This can be a huge advantage when performing math operations on large datasets. 

The array object in NumPy is called `ndarray` meaning 'n-dimensional array'.

Create a array:
### Create and print a NumPy array 'a' containing the elements 1, 2, 3.
a = np.array([1, 2, 3])
print(a)

the array would be  [1,x3]
[1, 2, 3]

Another way to implement an array is using `np.arange()`. This function will return an array of evenly spaced values within a given interval. To learn more about the arguments that this function takes, there is a powerful feature in Jupyter Notebook that allows you to access the documentation of any function by simply pressing `shift+tab`

### Create an array with 3 integers, starting from the default integer 0.
b = np.arange(3)
print(b)
b would be [0 1 2]


### Create an array that starts from the integer 1, ends at 20, incremented by 3.
c = np.arange(1, 20, 3)
print(c)
Output
[ 1  4  7 10 13 16 19]

What if you wanted to create an array with five evenly spaced values in the interval from 0 to 100? As you may notice, you have 3 parameters that a function must take. One paremeter is the starting number, in  this case 0, the final number 100 and the number of elements in the array, in this case, 5. NumPy has a function that allows you to do specifically this by using `np.linspace()`.

lin_spaced_arr = np.linspace(0, 100, 5)
print(lin_spaced_arr)

In this case arange(1, 20, 3) and  np.linspace(0, 100, 5) are the opposite in 
arange(1, 20, 3) we do not know how many elements there will be but we know that a1=1 , d=4 and ends up to 20. On the other hand lindspace(0,100,5) we know when it starts and how many spaces there will be but not specify the increment.


<mark style="background: #BBFABBA6;">The reason is that the default type for values in the NumPy function `np.linspace` is a floating point (`np.float64`)</mark>

If I want to change the dtype 

lin_spaced_arr_int = np.linspace(0, 100, 5, dtype=int)
print(lin_spaced_arr_int)
Output
[  0  25  50  75 100]

Now it is int!

char_arr = np.array(['Welcome to Math for ML!'])
print(char_arr)
print(char_arr.dtype) # Prints the data type of the array

Output:
['Welcome to Math for ML!']
<U23 `char_arr` array is `<U23`? This means that the string (`'Welcome to Math for ML!'`) is a 23-character (23) unicode string (`U`) on a little-endian architecture (`<`).


Numpy DataTypes : https://numpy.org/doc/stable/user/basics.types.html 

One of the advantages of using NumPy is that you can easily create arrays with built-in functions such as:

-   `np.ones()` - Returns a new array setting values to one.
-   `np.zeros()` - Returns a new array setting values to zero.
-   `np.empty()` - Returns a new uninitialized array.
-   `np.random.rand()` - Returns a new array with values chosen at random.
##### Return a new array of shape 3, filled with ones. 
ones_arr = np.ones(3)
print(ones_arr)

I can change it to int
ones_arr = np.ones(3, dtype =int)
print(ones_arr)
print(ones_arr.dtype)

Output
[1 1 1]
int64

##### Return a new array of shape 3, filled with zeroes.
zeros_arr = np.zeros(3)
print(zeros_arr)
[0. 0. 0.]

##### Return a new array of shape 3, without initializing entries.
empt_arr = np.empty(3)
print(empt_arr)
[0.91922229 0.05179767 0.8537525 ]

The memory spots randmly allocate a number to take this empy space within the memory.

#### Return a new array of shape 3 with random numbers between 0 and 1.
rand_arr = np.random.rand(3)
print(rand_arr)

In Numy you can create [[Multidimensional Arrays]]

Here you can do [[Indexing]] and [[Slicing]]