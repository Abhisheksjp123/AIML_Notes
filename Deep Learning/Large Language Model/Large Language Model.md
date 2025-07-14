Broad overview of what a large language model does to complete a sequence aka prompt,
Lets take an example
```
It rains a lot in the
```
We need a large language model to complete a sequence

The model takes the input tokens aka words and outputs probability distribution over its vocabulary
![[Screenshot 2025-07-04 at 11.42.48 PM.png | 200]]

**Vocabulary**: is set of words/tokens it has seen during its training

A high probability means that the model is more likely to give following next token the given input tokens.
Lets put this mathematically:
$$
LLM(X_1, ..., X_t) = P(X_{t+1} = v_i | X_1, ..., X_t)
$$