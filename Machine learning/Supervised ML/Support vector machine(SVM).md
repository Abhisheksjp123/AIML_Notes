Support Vector Machine (SVM) is a powerful supervised learning algorithm used for both classification and regression tasks. It works by finding the optimal decision boundary that separates different classes in the data.

## Core Concept

SVM aims to find the **hyperplane** that best separates classes by maximizing the **margin** - the distance between the decision boundary and the nearest data points from each class. These nearest points are called **support vectors**, which give the algorithm its name.

## How SVM Works

**Linear Separation**: For linearly separable data, SVM finds a straight line (2D), plane (3D), or hyperplane (higher dimensions) that separates classes with the maximum possible margin.

**Support Vectors**: Only the data points closest to the decision boundary (support vectors) influence the final model. Other points, even if removed, wouldn't change the decision boundary.

**Optimization Goal**: SVM solves an optimization problem to minimize classification error while maximizing the margin, creating a robust decision boundary that generalizes well to new data.

## Kernel Trick

When data isn't linearly separable, SVM uses **kernels** to transform the data into higher-dimensional spaces where linear separation becomes possible:

- **Linear Kernel**: For linearly separable data
- **Polynomial Kernel**: Creates curved decision boundaries
- **RBF (Radial Basis Function) Kernel**: Most popular, creates complex non-linear boundaries
- **Sigmoid Kernel**: Similar to neural network activation functions

## Key Parameters

**C Parameter**: Controls the trade-off between maximizing margin and minimizing classification errors. Higher C values create more complex boundaries but may overfit.

**Gamma Parameter**: For RBF kernels, controls the influence of individual training examples. Higher gamma creates more complex, localized decision boundaries.

## Advantages

SVM is effective in high-dimensional spaces and memory-efficient since it only uses support vectors. It's versatile with different kernel functions and works well when the number of dimensions exceeds the number of samples.

## Limitations

SVM can be slow on large datasets and doesn't provide probability estimates directly. It's sensitive to feature scaling and parameter selection, requiring careful preprocessing and tuning.

## Applications

SVM excels in text classification, image recognition, bioinformatics, and any scenario with high-dimensional data. It's particularly useful when you have a clear margin of separation between classes and need a robust, generalizable model.