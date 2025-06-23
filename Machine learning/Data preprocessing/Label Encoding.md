**Label Encoding**

- Converts categories to integers: "red"=0, "blue"=1, "green"=2
- Simple but can create false ordinal relationships

```
from sklearn.preprocessing import LabelEncoder
label_encoder = LabelEncoder()
train[cola] = label_encoder.fit_transform(train[cola])
test[cola] = label_encoder.transform(test[cola])
```