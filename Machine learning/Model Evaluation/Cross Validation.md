How to decide which data will be used for [[Train Test Split]]? To keep this unbaised ( for proper sampling) we use Cross validation. Cross validation uses the entire dataset as test and train on multiple iterations.  
  
for example 3 fold cross validation Splits the data into 3 parts , it uses the first two part for training and 3rd one for testing. Similarly this process is done 3 more time with all possible parmutation.  
finally average of all 3 model error is compared to select a better model unbiasedly.  
And model with the best fit amongst the 3 is Selected as the prediction model.  
Some popular Cross, validation methods are :  
1. 10 fold Cross validation :- used for large dataset  
2. Leave one out cross validation (use a Single point as test Set ) : - used for small dataset  
3. Stratified cross validation: adjusting test data of have similar measures of central tendency as training data  
  
Note*: common problem in cross validation,[[Data Leakage]] : using the same data for training and testing (results in overfitted model)  
  
In Case both the modes ( let say linear & Wigley line) have errors up and down across cross validation with overall error around same. In that Case we use statistics to decide or better model.