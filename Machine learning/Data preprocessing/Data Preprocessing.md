## Order Matters:

1. **[[Data Cleaning]]** (missing values, duplicates)
2. **[[Feature Engineering]]** (create new features)
3. **[[Train Test Split]]** (prevent data leakage)
4. **[[Encoding]]** (categorical variables)
5. **[[Feature Scaling]]** (fit on train, transform both train/test)
6. **[[Feature Selection]]** 

**Key Rule**: Always fit preprocessing on training data only, then transform both train and test sets.
This is to prevent [[Data Leakage]]
Also [[Sklearn Pipeline]] is generally used to tune and test several different combination of there data preprocessing and evaluation technique
Note* targett variable is common to all the independent variables hence it does not need any scaling


### 1. [[Data Cleaning]]
### 2. [[Feature Engineering]]

### 3. Data Transformation
1. [[Dimensionality Reduction]]
[[PCA (Principal Component Analysis)]]

2. [[Encoding]]
	1. [[Label Encoding]]
	2. [[One Hot Encoding]]

3. [[Feature Scaling]]
	1. [[Standardization]]
	2. [Normalizarion]
	3. [[Standardization vs Normalization]]

### 4. [[Feature Selection]]
1. Random Forest selection
### 5. [[Handelling imbalance data]]








