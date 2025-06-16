Carl Pearson developed PCA in 1901, and it is still relevant, and highly used in machine learning

Principal Component Analysis (PCA) is a dimensionality reduction technique that transforms high-dimensional data into a lower-dimensional space while preserving as much variance as possible


### Why PCA?
if we get rid of these less important or not important dimensions
1. Faster training
2. Data visualisation becomes easier with fewer dimensions
3. Also PCA and take 4 or more dimensions of data and plot them,
   This results in a scatter plot with PC1(or first principle component) on the X Axis, and 2nd principle component or PC2 on the y axis
   ![[Screenshot 2025-06-16 at 1.46.41 PM.png]]
4. Also it handles [[Curse of Dimensionality]]
   
   
### **What PCA does:**

- Finds the directions (principal components) along which data varies the most
- Projects data onto these new axes to reduce dimensions
- Orders components by how much variance they explain

**Principal Components:**

- Linear combinations of original variables
- First component explains maximum variance
- Each subsequent component explains maximum remaining variance
- Components are orthogonal (uncorrelated) to each other

#### How it does it(Maths behind PCA):
