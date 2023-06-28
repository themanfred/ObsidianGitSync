Using the [[Numpy library]]

![[Pasted image 20230503211128.png]]
With NumPy you can also create arrays with more than one dimension. In the above examples, you dealt with 1-D arrays, where you can access their elements using a single index. 

A multidimensional array has more than one column. <mark style="background: #FFB8EBA6;">Think of a multidimensional array as an excel sheet where each row/column represents a dimension.</mark>


#### Create a 2 dimensional array (2-D)
two_dim_arr = np.array([[1,2,3], [4,5,6]])
print(two_dim_arr)

Making matrices weee

[[1 2 3]
 [4 5 6]]
An alternative way to create a multidimensional array is by reshaping the initial 1-D array. Using `np.reshape()` you can rearrange elements of the previous array into a new shape. 

###### 1-D array 
one_dim_arr = np.array([1, 2, 3, 4, 5, 6])

#### Multidimensional array using reshape()
multi_dim_arr = np.reshape(
                one_dim_arr, # the array to be reshaped
               (2,3) # dimensions of the new array
              )
##### Print the new 2-D array with two rows and three columns
print(multi_dim_arr)
Output
[[1 2 3]
 [4 5 6]]

[[Attributes of an array]]
Find the size, dimension and shape of an array. These are all atrributes of a `ndarray` and can be accessed as follows:
