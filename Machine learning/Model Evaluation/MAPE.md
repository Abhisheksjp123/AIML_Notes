**MAPE (Mean Absolute Percentage Error)** measures prediction accuracy as a percentage.

**Formula:** MAPE = (1/n) × Σ|((y_actual - y_predicted) / y_actual)| × 100

**Step-by-step calculation:**

1. Calculate absolute error: |actual - predicted|
2. Divide by actual value: |actual - predicted| / actual
3. Take mean of all percentage errors
4. Multiply by 100 for percentage

**Key properties:**

- **Scale-independent**: Can compare across different datasets/units
- **Percentage format**: Easy to interpret (e.g., "5% average error")
- **Always positive**: Lower values = better model
- **Undefined for zero actual values**: Division by zero issue

**Advantages:**

- Easy to understand and communicate
- Good for comparing models across different scales
- Business-friendly metric

**Limitations:**

- **Asymmetric**: Penalizes over-predictions more than under-predictions
- **Undefined/problematic** when actual values are zero or near zero
- **Biased toward low forecasts**

**Example**: MAPE = 8% means your predictions are typically off by 8% of the actual value.
A MAPE of <5% is generally considered good


**In code (Python):**
```
def mape(y_actual, y_predicted):
    return np.mean(np.abs((y_actual - y_predicted) / y_actual)) * 100

# or using sklearn (if available)
from sklearn.metrics import mean_absolute_percentage_error
mape = mean_absolute_percentage_error(y_actual, y_predicted) * 100
```
