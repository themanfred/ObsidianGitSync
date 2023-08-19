Identify and attend to what's important.

Attention is the foundational mechanism of the [[transformer architecture]].

At it's core attention is the key operation 


The goal of the image (to understand):
![[Pasted image 20230721224920.png]]
1. Identify which parts to attend to 
2. Extract the features with high attention.
![[Pasted image 20230721225001.png]]


How does Search work:
Example: we want to learn about neural networks.

We may go to youtube to look at what is out there:
<mark style="background: #ADCCFFA6;">That is the Query (Q) - what we are looking for
We see the Key(s) (K) - The Titles related to the Query</mark>

![[Pasted image 20230721225658.png]]

Where we want to see how relevant is the key to the query.
- The turtle and koby bryan documentary are not relevant
- But the Deep Learning doc is highly relevant.

The final step now that we indentified a relevant video.
<mark style="background: #ADCCFFA6;">Return the related Value (V) - That are the most relevant to the Query</mark>

![[Pasted image 20230721230205.png]]

  Ex 2:
  We want to identify and attend the most important features in input
![[Pasted image 20230721230437.png]]
A NN layer is used to encode the positional info that captures the relative relationship in terms of order within the text.

So here we capture all this time step all at once.

Why? 
To understand the given information.

Then taking this postional embedding to understand where the words are (because it really does not comprehend it's meaning)

Where we extract a query, a key and a value and relating it to each other.
![[Pasted image 20230721230716.png]]

Attention applies a NN layer, transforming that  and giving a key to the given weights.

![[Pasted image 20230721230959.png]]
A sepaerate NN layer is created with a different set of weights, a different set of parameters.

Then this repeated with a different set of weghts to obtain value. Where we have a third layer.
![[Pasted image 20230721231131.png]]

Now with that Query, Key and Value. We can understand what is important and not and figure out where in that self input and what is important.

So here we will developing an Attention score: compute pairwise similarity between query and key.

Where we want to understand how how similar  they are.
Also known as <mark style="background: #CACFD9A6;">Cosine similarity</mark>

![[Pasted image 20230721231416.png]]

Which is the same as matrices ![[Pasted image 20230721231626.png]]

This opperation gives us a score:

How similar is the key  to the query?
![[Pasted image 20230721231653.png]]
We pass this through a [[softmax function]].

---

Now  that we have this metric to extract  features that deserve high attentions:
![[Pasted image 20230721231937.png]]

We can use this metric to extract this features, we get a transformation that reflect the features that are high attention.


Summary
---

The goal is to eliminate recurrance by focusing on the most important features in input.

First we get the input data, we compute the postitional encoding.
NN layers are applied with different weights to transform the Query, Key and Value matrices. 

We can then compute the self-attention weight score. According to the dot product operation that we went through prior.

Self attend to the features that should be given priority since they are most relevant  to extract features that deserve high attention.

![[Pasted image 20230721233339.png]]
.

This is sooooo powerful because the image above is the process of just one self attention head.

- Self-attention heads can plug into LNNs. Each head attends to different part of inputs.

![[Pasted image 20230721233714.png]]




