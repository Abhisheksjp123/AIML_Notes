Residuals should be normally distributed around mean 0.


Example and code:
```
# Residual
y_pred = model. predict(X_test)
residual = y_test - y_pred
```

Method1: Plot [[KDE(Kernel Density Estimation)]]

```
sns.displot(residual,kind='kde')
```
![[Screenshot 2025-06-27 at 6.47.31 PM.png | 400]]

Method 2: [[QQ Plot(Quantile Quantile plot)]]

```
# Q-Q plot
import scipy as sp
fig, ax = plt. subplots(figsize=(6,4))
sp. stats.probplot(residual, plot=ax, fit=True)
plt. show( )
```
![[Screenshot 2025-06-27 at 6.51.49 PM.png]]