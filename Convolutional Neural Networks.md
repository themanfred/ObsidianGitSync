They are a multi layer NN .

If you feed them pictures of edges it is going to be learning edges, higher up more specific as objects in the thing and the on the higher level it is the whole thing.

You can have different CNNs at the same time and act based on this.


Example:
![[Pasted image 20230410112214.png]]


For instance in this case I would like to identify the picture as an X or an O

![[Pasted image 20230410112257.png]]

SO NOT ALL Xs or Os are the same. for a computer is not easy.

![[Pasted image 20230410112328.png]]


Computers are literal so for them this are not the same image.

![[Pasted image 20230410112435.png]]

Features match pieces of the image
If you put the right feature and put it in the right right place.

![[Pasted image 20230410112629.png]]

Flitering:  The math behind the match
1. Line up the feature and the image patch
2. Multiply each image pixel by the corresponding feature pixel
3. Add them App
4. Divide bu the total number of pixels in the feature
5. ![[Pasted image 20230410112837.png]]
Because the feature and the the image patch is the same the ans is always 1  in this case. Now add a all of this ones and divide by 9 since there are 9 squares. equals 1
![[Pasted image 20230410113035.png]]
Now we go to a different feature and compare it to the same patch and notice we get a different result. By moving the feature around we can get a a map of how  much is matches the feature.
![[Pasted image 20230410113157.png]]

Convolution is the repeated application of this feature over and over again.

We repeat that with other features.
![[Pasted image 20230410113334.png]]


One image becase a stack of filtered images: This becomes a convolusion layer.
![[Pasted image 20230410113425.png]]

The next method is called pooling: Shrinking the image stack

1. Pick a window size (usually 2 or 3)
2. Pick a stride (usually 2)
3. Walk your window across your filtered images
4. From each window, take the maximum value
![[Pasted image 20230410113510.png]]

We determine the maximum value  here and move to the right and continue to do so and repeat.
![[Pasted image 20230410113901.png]]

What we end up is similar values but smaller
![[Pasted image 20230410114012.png]]

Shrinking it is convinient, the other thing pooling does is that pooling does not care where is that value positioned. It does not care if it is a little to the left if it is a little to the left or a little to the right.
![[Pasted image 20230410114125.png]]

In order to avoid this from breaking up and going to zero. Is turen the negative values to zero
![[Pasted image 20230410114155.png]]

Very similar image and do that with all the values
![[Pasted image 20230410114242.png]]

So we get this
![[Pasted image 20230410114314.png]]

Layers get stacked

The output of one becomes the input of the next
![[Pasted image 20230410114403.png]]

This can be done a bunch amount of times
![[Pasted image 20230410114433.png]]

![[Pasted image 20230410114541.png]]
Each of those is going to determine if they are or not  an X or a O in this case.

Some values will strongly suggest if it is an X or O. Based on the weights it you get a nice avg at the end

![[Pasted image 20230410114633.png]]

So in this case it will decide it is an X
![[Pasted image 20230410114814.png]]

![[Pasted image 20230410115037.png]]
![[Pasted image 20230410115051.png]]
Whoever gets the most votes wins.


So all of this can be stacked.
![[Pasted image 20230410115129.png]]


### Features in convolutional layers and voting weights in fully connected layers

That is done with backpropagation.
Error = right answer - actual answer
![[Pasted image 20230410115426.png]]

If we add all that up the error let's us deterime gradient descent

For each feature pixel and voting weight, adjust it up and down a bit and see how the error changes.


Doing that many times for lots of iterations and lots of steps help settle in a minimum. 

![[Pasted image 20230410115614.png]]

This are parameters that the designer gets to make.  No principal way on how to do this. 



This can be used for an 2d or 3d data. Things closertogether are more closely related than things far away.

Can do this with text and sound for example.

![[Pasted image 20230410120042.png]]

![[Pasted image 20230410120252.png]]


### Limitations 
ConvNets only capture local 'spatial' patterns in data. If the data can't be made to look like an  image, ConvNets are less useful.

