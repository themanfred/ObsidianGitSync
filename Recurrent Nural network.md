


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


Thee RNN is maintaing the state and it's updating the state at each of these time

![[Pasted image 20230712151946.png]]

RNNS have a state ht, updates this state over time.

How it starts


![[Pasted image 20230712152027.png]]

The RNN computation includes both this update f the hidden state and as welll generating an output at the end. The image below explains howÑ

Given some input vecor, it then perfomrs an update on the hidden state. Taking a weight matrix and multipying that vy the previous hidden state and taking another weight matrix time the input and applying the no linearity.

![[Pasted image 20230712153139.png]]
Then we can generate at a given time step by just by just modifying the hidden state. Using a different weight Matrix to update this value and the  generate a predicted output.


We can think of the RNN as a unrolling of all the states. We are Re'use the same weight matrices at every time  step 
![[Pasted image 20230712153419.png]]

We train this model, by defining the Loss. A prediction at an individual timestep. 

A prediction at a specific time step amounts to the loss at that time step, we can get the total loss by adding all the loss at each respective step.

![[Pasted image 20230712153844.png]]

Looking at  [[Tensorflow]] the RNN can be defined as a [[layer operation]] and a [[layer class]]

We can define it as the intialization of:
- weight matrices
- hidden states 
![[Pasted image 20230712154355.png]]
## RNNs for sequence modeling
![[Pasted image 20230712154655.png]]


To model sequences, we need to:

1. Handle **variable-lenght** sequences
2. Track **long-term** dependencies
3. Maintain information about **order**
4. **Share parameters** across the sequence
. 
## Design Criteria
![[Pasted image 20230712155148.png]]

#Example A sequence modeling problem: Predict the Next word:

"<mark style="background: #BBFABBA6;">This morning I took my cat for a</mark> <mark style="background: #FF5582A6;">walk</mark>."

	Given the words in green, predict word in red


- The NN is not equipped to handle language explicityly right.
- NN are simply mathematical operations

Define a way to translate this text this text into a numerical encoding. A vector (an array of numbers).

It works through [[Embedding]]