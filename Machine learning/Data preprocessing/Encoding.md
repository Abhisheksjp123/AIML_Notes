Machine learning algorithms work with numbers, but datasets often contain text categories like:

- Colors: "red", "blue", "green"
- Countries: "USA", "Canada", "Mexico"
- Product types: "electronics", "clothing", "books"

Algorithms can't directly process these text labels - they need numerical representations.

## Common Encoding Methods

1. [[Label Encoding]]
2. [[One Hot Encoding]]


```
from sklearn.preprocessing import LabelEncoder, OneHotEncoder
LabelEncoder()       # For ordinal: [Low, Medium, High] → [0,1,2]
OneHotEncoder()      # For nominal: [Red, Blue] → [1,0], [0,1]
pd.get_dummies()     # Pandas version of one-hot

```