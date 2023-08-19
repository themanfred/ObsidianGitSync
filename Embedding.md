Look at [[Deep Learning (NN)]]

![[Pasted image 20230712155649.png]]

Embedding is transforming indexes into a vector of fixed size.


1. We have all the vocubulary.
2. We index  each word to index.
3. We have a this fixed length vector of the size of out vocabulary. Each instance of the vocab, corresponds to a 1 at the corresponding index.
4. Otherwise it uses a RNN to create an encoding  or hidden meaning and putwords that are related or similar in a certain form closer together
![[Pasted image 20230712160137.png]]

**Note: Dependecies relate to order and sequences are defined by their order and we know that same words in a completely different order have different meaning**

![[Pasted image 20230712160413.png]]

---

So how do we train and learn the weights in the RNN, through [[Backproapagation Through Time (BPTT)]]


![[Pasted image 20230712164423.png]]




We vanishing gradients can be a real issue!

1. Multiply many small numbers together.
2. Erros due to further back time steps have smaller and smaller grandient 
3. Bias parameters to capture short-term dependencies

![[Pasted image 20230720234157.png]]

We may need to get data extensively from a very faraway input and the bigger the hap the bigher and more present this problems is

We can simply change the activation function, where they mitagate from shrinking the gradients.

### Trick 1
In all instances, where x is greater than 0 with the [[ReLu function ]], the derivative is 1.

![[Pasted image 20230720234209.png]]
### Trick 2

Initialize weights to identify matrix.
Initialize biases to zeo 
- This helps prevent the weights from shrinking to zero
![[Pasted image 20230720234406.png]]

### Trick 3: Gated cells
By controlling selectively the flow of info. into the neural unit. While mainting  what is important and the key and the most popular type of recurrent unit that achieves this gated computations is called [[Long short tem memory network (LSTM)]]

![[Pasted image 20230720234514.png]]
