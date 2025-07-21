AdaBoost (Adaptive Boosting) is a machine learning ensemble method that combines multiple weak classifiers to create a strong classifier. It's based on the principle that a collection of weak learners can perform better than any single strong learner.

## The Intuition

Imagine you're trying to identify spam emails. Instead of using one complex rule, AdaBoost uses many simple rules:

- Rule 1: "If email contains 'free money', it's spam"
- Rule 2: "If sender is unknown, it's spam"
- Rule 3: "If subject has excessive caps, it's spam"

Each rule alone isn't perfect, but together they form a powerful spam detector.

## The Algorithm Process

**1. Initialize Sample Weights** Every training example starts with equal weight: w₁ = 1/N (where N is the number of samples).

**2. For each iteration t:**

**Train Weak Learner**

- Train a weak classifier (decision stump which is a root node with 2 leaves) on the weighted training data
- The classifier focuses more on heavily weighted examples
- 
**Calculate Error Rate**

- εₜ = Σ(wᵢ × I(yᵢ ≠ hₜ(xᵢ))) / Σ(wᵢ)
- Where I() is an indicator function that equals 1 if prediction is wrong

**Calculate Classifier Weight**

- αₜ = 0.5 × ln((1 - εₜ) / εₜ)
- Better classifiers (lower error) get higher weights

**Update Sample Weights**

- For correctly classified: wᵢ = wᵢ × e^(-αₜ)
- For misclassified: wᵢ = wᵢ × e^(αₜ)
- Then normalize all weights

**3. Final Prediction** Combine all weak learners: H(x) = sign(Σ αₜ × hₜ(x))

## Key Characteristics

**Adaptive Learning** AdaBoost "adapts" by increasing weights on misclassified examples, forcing subsequent learners to focus on hard cases.

**Sequential Training** Unlike random forests where trees are independent, AdaBoost trains learners sequentially, with each learning from previous mistakes.

**Exponential Loss** AdaBoost minimizes exponential loss, which heavily penalizes misclassifications.
## Strengths and Weaknesses

**Strengths:**

- Excellent performance with simple weak learners
- Automatic feature selection
- Reduces both bias and variance
- Good theoretical foundations
- Fast prediction once trained

**Weaknesses:**

- Sensitive to noise and outliers
- Can overfit with noisy data
- Performance degrades with very weak learners
- Requires parameter tuning for optimal results

Example from StatQuest 