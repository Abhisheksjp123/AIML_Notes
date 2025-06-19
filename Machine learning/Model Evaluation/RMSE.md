**RMSE (Root Mean Squared Error)** measures the average magnitude of prediction errors.

**Formula:** RMSE = √(Σ(y_actual - y_predicted)² / n)

Where n = number of data points

**Step-by-step calculation:**

1. Calculate residuals: (actual - predicted) for each point
2. Square each residual
3. Take the mean of squared residuals (MSE)
4. Take the square root

**Key properties:**

- **Units**: Same as your target variable (unlike MSE)
- **Scale sensitive**: Larger errors get penalized more heavily
- **Always positive**: Lower values = better model
- **Interpretable**: Shows typical prediction error size

**Comparison with R²:**

- **R²**: Relative measure (0-1 scale), shows % variance explained
- **RMSE**: Absolute measure (in original units), shows typical error size

In code (Python):
```
from sklearn.metrics import mean_squared_error
import numpy as np

rmse = np.sqrt(mean_squared_error(y_actual, y_predicted))
# or
from sklearn.metrics import root_mean_squared_error
rmse = root_mean_squared_error(y_actual, y_predicted)
```