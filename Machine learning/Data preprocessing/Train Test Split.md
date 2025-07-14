## Why Split is Important for Regression

- **Training set**: Model learns relationships
- **Test set**: Evaluate how well model generalizes
- **Prevents overfitting**: Model can't memorize test data
- **Realistic performance**: Shows how model performs on unseen data

## Common Split Ratios

- 80/20 (most common)
- 70/30
- 90/10 (for large datasets)


Code
```
from sklearn.model_selection import train_test_split

# For regression
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

```
