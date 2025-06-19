```
# Handle missing values
df.fillna()          # Fill with mean/median/mode
df.dropna()          # Remove missing rows
df.interpolate()     # Interpolate missing values

# Remove duplicates
df.drop_duplicates()

# Handle outliers
df[df['column'] < threshold]  # Remove outliers

```