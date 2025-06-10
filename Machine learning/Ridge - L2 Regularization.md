![[Pasted image 20250610122011.png]]
A Ridge
"It's called Ridge" because it "shrinks" the weights toward zero (but not exactly to zero), smoothing the model."

Ridge regression is called L2 penalty because it adds the L2 [[norm]] of the coefficients to the loss function. Also known as L2 penalty

Example for a Linear models: 
Cost = SSR + λ∑(βᵢ²)
this ( λ x slope^2 ) is Called L2 /ridge penalty, it reduces dependence of independent Variable On dependent variable.

**How to select λ**
λ ≥ 0
It is determined by Cross validation

Ridge regression is also known as Tikhonov regularization, named after Andrey Tikhonov. "Sparse regularization" refers to LASSO.
Questions

[[Q3-Ridge regression is particularly effective for a) Feature selection b) Handling multicollinearity c) Creating sparse models d) Increasing model complexity.]]