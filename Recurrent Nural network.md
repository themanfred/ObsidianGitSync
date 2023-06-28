
![[Pasted image 20230408142452.png]]

Takes the values that are recieved and uses them along the new info to make predictions about tomorrow. Tomorrow's information the next day becomes yesterday's info for the day after and that is why it is recurring.

![[Pasted image 20230408142659.png]]
![[Pasted image 20230408142728.png]]
## Squashing function

Take all the votes and subjects them to this arctan function or tanh  where it crosses the version and no matter what happens the value will not exceed the -1 to 1 limits asthey approach infinity.

This way it will never explode!


This is an impporved architecture with memory included

![[Pasted image 20230408143015.png]]

### The cross  is element by element addition
![[Pasted image 20230408143128.png]]

### THe multiplication of each element
![[Pasted image 20230408143228.png]]

### Gating
![[Pasted image 20230408144050.png]]

The last signal was blocked and gating let's us control  what passes through or not

Therefore in the memory we will forget some values and remember others

### Logistic  function
Is like the sigmoid squashing function but it only goes from 0 to 1 so it takes the absolute value( sort of)
![[Pasted image 20230408144154.png]]


We have another neural  netwrok 

![[Pasted image 20230408144848.png]]

Long term memory 
![[Pasted image 20230408144958.png]]


Example:

We want to train a RNN on LSTM

For a children's book

![[Pasted image 20230408145151.png]]

It just saw the word <mark style="background: #ADCCFFA6;">Doug</mark>  and it predicts it should see the word <mark style="background: #FFF3A3A6;">saw</mark>.
Doug is in black becasue it does not want to see it again for a while and saw in white 


The word saw is going be sent out 
![[Pasted image 20230408145433.png]]


THe forgetting gate has saw, Doug and there is a negative vote for Doug and a postitive vote for Doug so it cancels out
![[Pasted image 20230408145513.png]]

So it avoids Doug because it avoids a Doug saw Doug error and only Jane and Spot are passed

![[Pasted image 20230408145639.png]]

Where is this practical!

Sequential patterns
- Text
- Speech
- Audio
- Video
- Physical processes
- Anything embedded in time (almost everything)
- Robotics
### Main NN components that make up a LSTM

- prediction 
- ignoring
- forgetting
- selection
- 
