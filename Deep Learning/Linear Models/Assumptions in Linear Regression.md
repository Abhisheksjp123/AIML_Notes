The key assumptions of linear regression are:

1. **[[Linearity]]** - The relationship between independent and dependent variables is linear
2. **No [[Multicollinearity]]** - Independent variables are not highly correlated with each other
3. **Independence** - Observations are independent of each other
Ex: [[Time series modelling]] data explicitly violates the independence assumption. Each observation depends on previous time points, which is actually the core feature of time series analysis.

==next three assumptions are based on residuals==
3. **[[Homoscedasticity]]** - Constant variance of residuals across all levels of independent variables
4. **[[Normal Residuals]]** - Residuals are normally distributed
5. **No [[Autocorrelation]]** - Residuals are not correlated with each other (especially important for [[Time series modelling]])