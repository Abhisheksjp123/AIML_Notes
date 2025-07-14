**matplotlib subplots** - creating multiple plots in one figure. Very common pattern:

## Basic Subplot Structure
```
import matplotlib.pyplot as plt

# Create figure with multiple axes
fig, axes = plt.subplots(1, 3)  # 1 row, 3 columns

# Plot on each axis
axs[0].hist(df['Age']).axes
axs[1].hist(df['Annual Income (k$)'])
axs[2].hist(df['Spending Score (1-100)'])

plt.show()

```
![[Screenshot 2025-06-28 at 1.51.58 AM.png]]

## Common Patterns You'll See

### 2x2 Grid (4 plots)
```
fig, axes = plt.subplots(2, 2, figsize=(12, 10))

axes[0,0].hist(df['income'])                    # Top-left
axes[0,1].hist(df['income'], bins=50)           # Top-right  
axes[1,0].boxplot(df['income'])                 # Bottom-left
axes[1,1].scatter(range(len(df)), df['income']) # Bottom-right
```

Different Plot Types
```
fig, (ax1, ax2, ax3) = plt.subplots(1, 3, figsize=(15, 5))

ax1.hist(df['income'])
ax2.hist(np.log(df['income']))  # Log-transformed
ax3.plot(df['income'])          # Line plot
```

## Why People Do This

- **Compare different views** of same data (normal vs log scale)
- **Compare different binning** (bins=20 vs bins=100)
- **Multiple variables** side by side
- **Before/after transformations**
- **Clean presentation** - everything in one figure