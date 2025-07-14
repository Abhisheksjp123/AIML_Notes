**K-Nearest Neighbors (KNN)** is a simple, non-parametric( see [[Parametric vs non Parametric]]) algorithm that classifies data points based on their k closest neighbors.

**How it works:**

1. Store all training data
2. For a new point, find the k nearest neighbors
3. For classification: majority vote among k neighbors
4. For regression: average of k neighbors' values

**Key Components:**

- **K value**: number of neighbors to consider
- **Distance metric**: usually Euclidean distance
- **Voting**: majority class wins

**Example - Obesity Prediction:**

```
Training data: Age, Exercise, BMI → Class
New person: Age=35, Exercise=2, BMI=28

Find 3 nearest neighbors:
Neighbor 1: Age=33, Exercise=1, BMI=29 → Obese
Neighbor 2: Age=37, Exercise=3, BMI=27 → Not Obese  
Neighbor 3: Age=36, Exercise=2, BMI=30 → Obese

Majority vote: 2 Obese, 1 Not Obese → Predict Obese
```

**Choosing K:**

- **K=1**: Very sensitive to noise
- **Large K**: Smoother decision boundary
- **Odd K**: Avoids ties in binary classification

**Advantages:**

- Simple to understand and implement
- No training period
- Works well with small datasets
- Non-linear decision boundaries

**Disadvantages:**

- Slow prediction (must compute all distances)
- Sensitive to irrelevant features
- Requires feature scaling
- Poor with high-dimensional data