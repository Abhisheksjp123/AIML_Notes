There should be no correlation between the independent variables each of them. 
i.e on changing one variable another variable should remain constant
Why this is so important?
Equation of of linear reg will be like
$$
Y = β₀ + β₁X₁ + β₂X₂ + β₃X₃ + ε
$$
the main work of lin reg is to find out these coeff. betas.
What does they signify?
β₁ signifies what will be the change in Y when X₁ is modified, ==given all other variables remain constant== this is important. as if there is a correlation, that true picture cannot be built.


#### Example and code to test multicollinearity in your data

[[Variance inflation Factor]] is an important method to test multicollinearity in your data
```
from statsmodels.stats.outliers_influence import variance_inflation_factor as VIF

vif = []

for i in range(X_train.shape[1]) :

vif.append(variance_inflation_factor(X_train, i))

pd.DataFrame({'vif': vif}, index=df.columns [0:3]).T
```
![[Screenshot 2025-06-27 at 6.32.04 PM.png]]

if VIF is around 1 there is no multicollinearity if it is 5 or more than 5, there is multicollinearity.



==Another method==(Though VIF is the preferred one)
is create collinearity plot b/e all the variables\
```
# Another Technique
sns.heatmap(df.iloc[:,0:3] .corr), annot=True)
```


![[Screenshot 2025-06-27 at 6.36.30 PM.png]]