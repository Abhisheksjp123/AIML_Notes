==**Interpretable Models** ==are inherently transparent - their structure and decision process are naturally understandable to humans. These models are "glass boxes" where you can directly observe how inputs lead to outputs. Examples include:

- Linear regression (coefficients show feature importance)
- Decision trees (clear if-then rules)
- Logistic regression (interpretable coefficients)
- Simple rule-based systems

With interpretable models, understanding comes from the model's architecture itself. You can look at a decision tree and trace exactly why a particular decision was made.

==**Explainable Models**== (or more accurately, models made explainable through post-hoc explanation methods) are typically complex "black box" models that require additional techniques to understand their behavior. These include:

- Deep neural networks
- Random forests
- Support vector machines
- Ensemble methods

For these models, we use explanation techniques like [[LIME]], [[SHAP]], attention mechanisms, or feature importance scores to understand what the model learned and why it made specific predictions.