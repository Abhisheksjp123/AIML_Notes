```
from sklearn.preprocessing import LabelEncoder, OneHotEncoder
LabelEncoder()       # For ordinal: [Low, Medium, High] → [0,1,2]
OneHotEncoder()      # For nominal: [Red, Blue] → [1,0], [0,1]
pd.get_dummies()     # Pandas version of one-hot

```