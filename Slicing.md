Slicing gives you a sublist of elements that you specify from the array. The slice notation specifies a start and end value, and copies the list from start up to but not including the end (end-exclusive). 


<mark style="background: #ADCCFFA6;">The syntax is:

`array[start:end:step]`
</mark>
If no value is passed to start, it is assumed <mark style="background: #ABF7F7A6;">`start = 0`</mark>, if no value is passed to end, it is assumed that <mark style="background: #D2B3FFA6;">`end = length of array - 1`</mark> and if no value is passed to step, it is assumed <mark style="background: #CACFD9A6;">`step = 1`</mark>.


#### Slice the array a to get the array [2,3,4]
sliced_arr = a[1:4]
print(sliced_arr)

Output:
[2, 3, 4]

#### Slice the array a to get the array [1,2,3]
sliced_arr = a[:3]
print(sliced_arr)

Output:
[1, 2, 3]


#### Slice the array a to get the array [3,4,5]
sliced_arr = a[2:]
print(sliced_arr)

[3, 4, 5]

#### Slice the array a to get the array [1,3,5]
sliced_arr = a[::2]
print(sliced_arr)

[1, 3, 5]

#### Note that a == a[:] == a[::]
print(a == a[:] == a[::])
True



Note: do slicing excercises

Very usefull
