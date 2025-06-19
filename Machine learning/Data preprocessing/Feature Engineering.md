```
# Create new features
df['total'] = df['price'] * df['quantity']

# Binning continuous variables
pd.cut(df['age'], bins=[0,18,65,100], labels=['child','adult','senior'])

# Date/time features
df['year'] = df['date'].dt.year
df['day_of_week'] = df['date'].dt.dayofweek
```