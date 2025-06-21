**What F-statistic tests:**

- **Null hypothesis (H₀)**: All coefficients = 0 (R² = 0, model explains nothing)
- **Alternative (H₁)**: At least one coefficient ≠ 0 (model explains some variance)

**F-statistic formula:** F = (R²/k) / ((1-R²)/(n-k-1))

Where:

- **k** = number of predictors
- **n** = sample size
- **R²** = coefficient of determination

**Interpretation:**

- **High F-value + Low p-value** → R² is statistically significant
- **Low F-value + High p-value** → R² might be due to chance

**What this means:**

- F-test tells you if your **overall model** is better than just using the mean
- **Doesn't tell you which specific variables** are significant (that's t-tests for individual coefficients)
- **Doesn't tell you if R² is practically meaningful** (0.05 might be significant but useless)

**Example:**

- R² = 0.7, F = 25.4, p < 0.001 → Model significantly explains 70% of variance
- R² = 0.02, F = 1.2, p = 0.3 → 2% might just be random noise

**Key point:** F-statistic validates whether your R² represents real relationships or just statistical noise.