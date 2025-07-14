To test how well a model perform we collect some more data and test our prediction on that data.
This data is called **Training data** while the data on which the model is created is called Testing data . This is called Train and Test split of data.
![[Pasted image 20250617145305.png]]
As we Can See even though model 2 fits better on the training set (**overfitting**) If performs bad in prediction.

Now we calculate different [[Model evaluation metrics]] based on our requirement like:  
A. Quantitative metrics
1. [[R Square]]
2. [[MAPE]]
3. [[RMSE]]
B. Classification metrics
4. Confusion matrix based matrices(Precision, recall, sensitivity and specificity)

[[Q7-What is Bias variance trade off]]

There can always be bias in training and testing data split, and the split sample might not capture the full image of the data. Here [[Cross Validation]] is used


