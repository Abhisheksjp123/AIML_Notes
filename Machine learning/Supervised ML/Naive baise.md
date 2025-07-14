**Naive Bayes** is a probabilistic classifier based on Bayes' theorem with a "naive" assumption of feature independence.
[[Bayes Theorem]]
$$
P(Class|Features) = P(Features|Class) × P(Class) / P(Features)
$$
Then important thing here is the **The "Naive" Assumption:** Features are conditionally independent given the class:
$$
P(x₁,x₂,x₃|Class) = P(x₁|Class) × P(x₂|Class) × P(x₃|Class)
$$
**Types of Naive Bayes:**

1. **Gaussian NB**: Continuous features (normal distribution)
2. **Multinomial NB**: Discrete counts (text classification)
3. **Bernoulli NB**: Binary features

Obesity Prediction Example:
Features: Age, Exercise, BMI 
Classes: Obese, Not Obese

$$
P(\text{Obese}|\text{Age}=35, \text{Exercise}=2, \text{BMI}=28) = \frac{P(\text{Age}=35|\text{Obese}) \times P(\text{Exercise}=2|\text{Obese}) \times P(\text{BMI}=28|\text{Obese}) \times P(\text{Obese})}{P(\text{Age}=35, \text{Exercise}=2, \text{BMI}=28)}
$$


**Training Process:**

1. Calculate P(Class) for each class
2. For each feature, calculate P(Feature|Class)
3. Store these probability distributions

**Prediction:**

1. Calculate P(Class|Features) for each class
2. Choose class with highest probability

**Advantages:**

- Fast training and prediction
- Works well with small datasets
- Handles multiple classes naturally
- Good baseline model

**Disadvantages:**

- Strong independence assumption (rarely true)
- Can be outperformed by more sophisticated models
- Sensitive to skewed data

**Common Use Cases:**

- Text classification (spam detection)
- Medical diagnosis
- Real-time predictions

Despite the "naive" assumption, it often performs surprisingly well in practice!