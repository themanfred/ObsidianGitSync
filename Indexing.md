Indexing is very useful as it allows you to <mark style="background: #BBFABBA6;">select specific elements from an array</mark>. It also lets you select entire rows/columns or planes as you'll see in future assignments for multidimensional arrays. 

##### Select the third element of the array. Remember the counting starts from 0.
a = ([1, 2, 3, 4, 5])
print(a[2])

##### Select the first element of the array.
print(a[0])

3
1

For multidimensional arrays of shape `n`, to index a specific element, you must input `n` indices, one for each dimension.
#### Indexing on a 2-D array
two_dim = np.array(([1, 2, 3],
          [4, 5, 6], 
          [7, 8, 9]))

#### Select element number 8 from the 2-D array using indices i, j.
print(two_dim[2][1])