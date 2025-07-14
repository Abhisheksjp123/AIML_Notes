A feedforward network is the simplest type of neural network where information flows in one direction only - from input to output, without loops or cycles.

**Structure:**

- **Input layer** → **Hidden layer(s)** → **Output layer**
- Information moves forward through layers sequentially
- No connections backward or within the same layer

**Key characteristics:**

- **Acyclic**: No feedback loops
- **Layer-wise**: Each layer connects only to the next layer
- **Static**: Output depends only on current input (no memory)

**Basic operation:**

```
Input → Linear transformation → Activation → Next layer → ... → Output
```

**Common architectures:**

- **Perceptron**: Single layer (no hidden layers)
- **Multi-layer perceptron (MLP)**: Multiple hidden layers
- **Deep feedforward**: Many hidden layers

**Use cases:**

- Classification problems
- Regression tasks
- Function approximation
- Pattern recognition

**Contrast with other types:**

- **Recurrent networks**: Have feedback connections (memory)
- **Convolutional networks**: Specialized feedforward networks for images

MLPs are the most common feedforward networks and form the building blocks for more complex architectures.