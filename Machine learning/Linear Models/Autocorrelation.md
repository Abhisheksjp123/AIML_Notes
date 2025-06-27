**Autocorrelation** means residuals (prediction errors) are correlated with each other in a pattern.

**Simple example:** If your model consistently under-predicts for several observations in a row, then over-predicts for the next several - that's autocorrelation.

**What it looks like:**

- Residual at time t is related to residual at time t-1
- Creates patterns in residual plots instead of random scatter
- Often shows up as waves or cycles in residual vs. fitted plots

**Why it's bad:**

- Your model is missing systematic patterns in the data
- Standard errors are underestimated (you think you're more accurate than you are)
- Confidence intervals are too narrow

**Common causes:**

- **Time series data** - today's error relates to yesterday's
- **Missing variables** - systematic patterns you haven't captured
- **Wrong functional form** - maybe you need polynomial terms

**How to detect:**

- Plot residuals vs. time/order
- Durbin-Watson test
- Look for patterns rather than random scatter

**The assumption**: Residuals should be random noise with no predictable pattern. If you can predict one residual from another, your model is incomplete.

code
simply plot the residuals and check if it dosen't follows any pattern
```
plt.plot(residuals)
```