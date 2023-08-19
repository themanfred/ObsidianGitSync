![[Pasted image 20230720234726.png]]
![[Pasted image 20230720234756.png]]
LSTM cells are able to track information throught many timesteps.

# Key concepts LSTM
1. Mantain a cell state, standard [[Deep Learning (NN)]]
2. Use gates to control the flow of information 
	1. Forget gate gets rid of irrelevant information
	2. Store relvant information from current input
	3. Selectively update cell state
	4. Output gate returns a filtered version of the cell state.

