**Lasso**: Least absolute shrinkage and selection operator, its like using a lasso to rope in the most important factor and ignore the rest.

it is extremely Similar to [[Ridge - L2 Regularization]] but with important distinction, it adds the L1 [[norm]] of the coefficients to the loss function. Also known as L1 penalty

Example for a Linear models: 
Cost = SSR + λ∑(|βᵢ|)
this ( λ x |slope| ) is Called L1 /Lasso penalty