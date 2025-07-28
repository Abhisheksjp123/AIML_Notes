## Few Shot Prompt:
**Definition**: Few shot prompting is a prompt engineering technique where you insert examples in your prompt, training the model on what you want the output to look and sound like. This method builds on LLM's ability to learn and generalize information from a small amount of data.
How It Works:
Few-shot prompting can be used as a technique to enable in-context learning where we provide demonstrations in the prompt to steer the model to better performance. The demonstrations serve as conditioning for subsequent examples where we would like the model to generate a response
```
Classify the sentiment as positive, negative, or neutral.

Example: "I love this product!" → Positive
Example: "This is terrible." → Negative
Example: "It's okay, I guess." → Neutral

Classify: "The weather is nice today."
```
