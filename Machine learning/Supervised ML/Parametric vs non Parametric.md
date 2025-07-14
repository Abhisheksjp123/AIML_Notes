**Parametric models (like logistic regression):**

- Have a **fixed number** of parameters regardless of data size
- Learn parameters (β₀, β₁, β₂, etc.) from training data
- After training, can **discard** training data
- Make assumptions about data distribution
**Non-parametric models (like KNN):**

- Number of "parameters" **grows with data size**
- **Store all training data** - the data itself becomes the "model"
- No fixed functional form
- Make fewer assumptions about data distribution

So for larger dataset parametric models are better in computation as compared to non parametric model