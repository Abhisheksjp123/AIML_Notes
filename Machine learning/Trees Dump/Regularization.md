**Summary:** 
**regularisation techniques** in machine learning, primarily focusing on **Ridge (L2)** and **Lasso (L1)**regression, and their combination, **ElasticNet**. **Regularisation** is introduced as a method to prevent **overfitting** by adding a penalty for model complexity, promoting simpler models. The key distinction between Ridge and Lasso lies in their penalty types: Ridge shrinks coefficients close to zero but not exactly, making it effective for **multicollinearity**, while Lasso can shrink coefficients to zero, performing **feature selection**. **ElasticNet** combines both approaches. It is also highlighted that **feature scaling** is crucial for regularised regression because the penalties are scale-dependent.


**Theory**
Regularization is a technique in Machine learning to prevent Overfitting, i.e when a model learns the training data too well, Includes noise and work poorly on new data. It does this by adding more bias by adding penalty to models complexity, encouraging simple models that generalize better. That is where the word regularization comes, making regular not complex model.

[[Q1-Why is overfitting needs to be treated separately with Regularization but underfitting is not]]

This is achieved by 2 types of penalties:
1. [[Ridge - L2 Regularization]]
2. [[Lasso - L1 Regularization]]

[[Q2-How are Ridge and Lasso different and where should one be preferred over another]]
3. [[ElasticNet Regularization]]



Questions:
[[Q4-Feature scaling is important for regularized regression because{MCQ}]]