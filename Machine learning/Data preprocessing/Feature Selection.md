```
from sklearn.feature_selection import SelectKBest, RFE
SelectKBest(k=10)    # Select top k features
RFE(estimator, n_features_to_select=5)  # Recursive elimination
```