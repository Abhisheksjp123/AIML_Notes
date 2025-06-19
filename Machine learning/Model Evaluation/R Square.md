R-squared (R²) measures how well your model explains the variance in the target variable.

**Formula:** R² = 1 - (SS_res / SS_tot)

Where:

- **SS_res** = Sum of Squared Residuals = Σ(y_actual - y_predicted)²
- **SS_tot** = Total Sum of Squares = Σ(y_actual - y_mean)²

**Interpretation:**

- R² = 1: Perfect fit (model explains 100% of variance)
- R² = 0: Model performs as well as just using the mean
- R² < 0: Model performs worse than using the mean

**In code (Python):**
```
from sklearn.metrics import r2_score
r2 = r2_score(y_actual, y_predicted)
```

Also Read:
[[Adjusted R Square]]