To evaluate model performance, we use separate data that the model hasn't seen during training. This unseen data is called **testing data**, while the data used to create the model is called **training data**. This separation process is called **train-test split**.

## Q. What is Validation data and how it is different from testing data
Ans: 
The **testing set** and **validation set** are both used in machine learning to evaluate model performance, but they serve **different purposes** and are used at **different stages** of model development.
==Validation Set:==
Used during model development to tune hyperparameters and select the best model. It is created after training set before final , Helps avoid overfitting by giving feedback during training.
Example: Choosing the number of layers in a neural network, or tuning `k` in k-nearest neighbors.
Think of it as your **practice exam** before the final test.
==**Testing data:**==
Used **only once** after all tuning is complete to estimate how well your model will perform on unseen data. Created After training and validating are done. It provides an unbiased evaluation of the final model. used to report final accuracy, precision, recall, etc.
This is your **final exam** — the score you show to the world.
Test set is kept separate to avoid [[Data Leakage]]

Diagram (Typical Workflow):
```
Dataset
  └── Split ──► Train Set (e.g. 70%)
               ├─ Train model
               └──► Validation Set (e.g. 15%)
                    └─ Tune model (hyperparameters)
                         ↓
                     Final Model
                         ↓
                   Test Set (e.g. 15%)
                         └─ Final evaluation

```


## Once we have our testing data, we evaluate model performance using appropriate [[Model Evaluation Metrics]] based on our problem type:

**A. Regression Metrics (Quantitative)**

1. [[R Square]] - Explains variance in target variable
2. [[MAPE]] - Mean Absolute Percentage Error
3. [[RMSE]] - Root Mean Square Error

**B. Classification Metrics** 
4. **Confusion Matrix-based metrics**: Precision, Recall, Sensitivity, Specificity
5. Additional metrics: F1-score, ROC-AUC

## **Limitations of Single Train-Test Split:**

- **Sampling bias**: The specific split may not represent the full dataset
- **Variance in results**: Different splits can yield different performance estimates
- **Limited data utilization**: Some data remains unused for training

**Solution: [[Cross Validation]]** Cross-validation addresses these limitations by using multiple train-test splits, providing more robust and reliable performance estimates.

