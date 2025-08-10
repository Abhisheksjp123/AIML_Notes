# Data Preprocessing and EDA

## **1. Understanding Data**
Load data
Check shapes
Column types
Basic stats

## **2. Data type fixes**
Convert to proper types (e.g., dates to `datetime`, numbers from strings).
"Generally in modelling in max models we need numerical data types"
## **3. Missing Value Handling**
Find nulls.
Fill, drop, or impute as per strategy.
## **4. Outlier Detection & Treatment**

Do Visual check after NaNs are handled. like histograms etc
Techniques for outlier removal: 
1. Percentile capping: Simply remove the outlier below 1%ile and above 99th %ile
2. [[IQR]]:
   IQR = Q3-Q1 it helps to create a nominal lower bound and upper bound for a variable
3. [[Z-Score method]] : 

## **5. Data Consistency Checks**
Fix category spelling issues, unit mismatches, duplicates.

## **6. Feature Engineering**
 Create new features, bin continuous values, extract date parts, etc.

## **7. Encoding Categorical Variables**
Label encode or one-hot encode depending on type.

## **8. Feature Scaling**
Standardize, normalize, or use robust scaling.

## **9. EDA Insights**
Univariate, bivariate, and correlation analysis.

## **10. Train-Test Split & Modeling Prep**
**Save clean dataset and proceed to modeling.**


# Data Modelling

[[Q9 - How to select an ML model]]
