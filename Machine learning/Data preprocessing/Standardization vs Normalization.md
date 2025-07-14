**they're different!** This is a common confusion. Let me clarify:

## [[Standardization]]≠ [[Normalization]]

Code to apply both
```
from sklearn.preprocessing import StandardScaler, MinMaxScaler

# STANDARDIZATION (StandardScaler)
scaler = StandardScaler()
X_standardized = scaler.fit_transform(X)
# Result: mean=0, std=1, range=(-∞, +∞)

# NORMALIZATION (Min-Max)
scaler = MinMaxScaler()
X_normalized = scaler.fit_transform(X)
# Result: range=[0, 1]

```
## When to Use Which:

**StandardScaler:**

- Data follows normal distribution
- Features have different units/scales
- Algorithms like SVM, Neural Networks, PCA

**MinMaxScaler:**

- Want bounded range [0,1]
- Data doesn't follow normal distribution
- Algorithms sensitive to outliers

**For Clustering:**

- Both work, but StandardScaler is more common
- Try both and see which gives better results!