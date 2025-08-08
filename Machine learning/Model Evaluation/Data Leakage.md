Data leakage occurs when information from outside the training period inappropriately influences model training, leading to overly optimistic performance estimates.

**Common causes:**

- **Preprocessing on entire dataset**: Applying standardization, normalization, or feature scaling to the full dataset before train/test split
- **Feature engineering**: Creating features using statistics from the complete dataset
- **Target leakage**: Using future information or variables that won't be available at prediction time

**Prevention:**

- Always split data first, then preprocess training and test sets separately
- Use only training data statistics for transformations, then apply to test set
- Implement proper cross-validation with preprocessing inside each fold

**Impact:** Models appear to perform better than they will in production, creating false confidence in model accuracy.