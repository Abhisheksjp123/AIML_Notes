Neural networks are computational models inspired by biological brain networks. They consist of interconnected nodes (neurons) organized in layers that process information by passing weighted signals between them.

Key components:

- **Input layer**: Receives data
- **Hidden layers**: Process information through weighted connections
- **Output layer**: Produces results
- **Weights and biases**: [[NN Parameters]] that determine signal strength and processing

They learn by adjusting these weights through training on data, using algorithms like [[Backpropagation]]. Common types include [[Feedforward networks]], [[Convolutional neural networks (CNNs)]] for images, and [[Recurrent neural networks (RNNs)]] for sequences.

Neural networks power most modern AI applications including image recognition, natural language processing, and machine learning systems.

Example use case
Lets say we've a drug to treat illness , and we've 3 groups of people who are given 3 different dosages (low, medium, high)
![[638866497801006777.png| 200]]
Now, we want to predict weather the future dosages will be effective or not  
we can not solve it through a linear line , the good thing is NN can fit a wiggle to the data
![[638866498335765216.png|200]]
It can even fit a wiggle to this
![[Pasted image 20250627193919.png]]

Note: the [[NN Parameters]]/weighted signals can be complex but for simplicity we'll take
$$
y = Wx + b
$$
where W: weight
b: bias

Example of a complete fitted simple NN with parameters calculated through [[Backpropagation]]
![[638866503780322530.png]]


Notice the curved line inside the nodes, these curved lines are the building blocks for fitting a wiggle to the data. These identical curves can be reshaped by the parameter value and then added together to get the green wiggle that fits the data. This lines are called [[Activation functions]]
Note* (In tutorials you'll see people Using sigmoid function frequently but in practice Relu /soft plus are more popular )

Note* this is a very simple NN with 1 input node , 1 output node and 2 middle node  
but in actual NN are much fancier, the middle layers are called hidden layers , and you've to decide how many hidden layers to have and nodes in each layer while creating a NN.
![[638866509652316272.png|400]]

While creating a NN you've to decide not of hidden layers, number of nodes in the hidden layer and [[Activation functions]] to use

Let's see how NN fits in above example
![[638866516319631147.png|300]]

let's keep the dosage 0 for low 1 for high, Now if we input 0 and pass it through first parameter value we'll get 2.14
 $$
  P_1 = -34.4x + 2.14
  $$
  ![[638866518818334636.png|400]]
  To get the y-axis output of softplus function we'll put 2.14 in this eq
  $$
  F(x) = ln(1+e^{x})
$$
for all the dosage value output will look like:
![[638866520115071078.png|300]]
now we pass it through 2nd part of Parameter Value and end up with new blue curve
$$
P_2 = -1.3x
$$
![[638866521197192322.png]]
similarly we draw a curve from input node to the bottom node of NN , and we got following orange curve
![[638866521470108692.png]]
  Now the NN tells us to add the y-axis Coordinate of orange curve and green curve , and this gives us the green wiggle, and after substructing-0.58 from it we get
  ![[638866521975738438.png]]


Now let see how NN optimize the weights and bias aka parameters through: [[Backpropagation]]

