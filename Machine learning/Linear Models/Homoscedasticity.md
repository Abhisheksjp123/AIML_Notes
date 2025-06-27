Homo - Same
Scedasticity - scatter

i.e when you plot your residuals its spread should be equal.

Example, 
![[Screenshot 2025-06-27 at 6.54.13 PM.png]]
Plot 1 follow [[Homoscedasticity]] but other two follows Heteroscedasticity

Code:
you can simply plot a scatter plot b/w residuals and y_pred to check this
```
plt.scatter(y_pred,residual)
```