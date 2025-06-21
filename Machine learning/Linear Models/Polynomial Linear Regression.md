Polynomial regression is linear regression with **engineered polynomial features**.

**Process:**

1. **Feature Engineering**: Create new features from existing ones
    - x → x, x², x³, x⁴...
    - For multiple variables: x₁, x₂, x₁², x₂², x₁x₂, etc.
2. **Still Linear**: y = β₀ + β₁x + β₂x² + β₃x³ + ...
    - Linear in **coefficients** (β), not necessarily in **features** (x)
3. **Automatic Feature Selection**:
    - If polynomial terms don't improve fit → coefficients ≈ 0
    - **Regularization** (Ridge/Lasso) can force irrelevant polynomial coefficients to exactly 0

**Example:**

python

```python
# Manual feature creation
X_poly = [x, x², x³, x⁴]
# Then regular linear regression
y = β₀ + β₁x + β₂x² + β₃x³ + β₄x⁴
```

**Key Insights:**

- **"Linear" in Linear Regression** refers to coefficients, not features
- **Same algorithm** (OLS), just different input features
- **Higher-order terms** capture non-linear relationships
- **Overfitting risk** increases with degree (regularization helps)

**Result:** If data truly follows y = 2x + 3, then coefficients for x², x³... will be ≈ 0.

So yes, it's just linear regression with polynomial feature engineering!