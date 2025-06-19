```
# K-MEANS CLUSTERING - Quick Reference

# IMPORTS
from sklearn.cluster import KMeans
from sklearn.datasets import make_blobs
import matplotlib.pyplot as plt
import numpy as np

# BASIC USAGE
# 1. Create model with hyperparameters
kmeans = KMeans(
    n_clusters=3,           # k - number of clusters
    init='k-means++',       # initialization method
    max_iter=300,          # max iterations
    random_state=42        # for reproducibility
)

# 2. Fit the model
kmeans.fit(X)

# 3. Predict clusters
labels = kmeans.predict(X)
# OR fit and predict together
labels = kmeans.fit_predict(X)

# ACCESS RESULTS
centroids = kmeans.cluster_centers_
inertia = kmeans.inertia_  # within-cluster sum of squares

# ELBOW METHOD - Find optimal k
def elbow_method(X, max_k=10):
    inertias = []
    k_range = range(1, max_k + 1)
    
    for k in k_range:
        kmeans = KMeans(n_clusters=k, random_state=42)
        kmeans.fit(X)
        inertias.append(kmeans.inertia_)
    
    plt.plot(k_range, inertias, 'bo-')
    plt.xlabel('k')
    plt.ylabel('Inertia')
    plt.title('Elbow Method')
    plt.show()

# COMPLETE EXAMPLE
X, _ = make_blobs(n_samples=300, centers=4, random_state=42)

# Find optimal k
elbow_method(X, max_k=8)

# Apply K-means with optimal k
kmeans = KMeans(n_clusters=4, random_state=42)
labels = kmeans.fit_predict(X)

# Plot results
plt.scatter(X[:, 0], X[:, 1], c=labels, cmap='viridis')
plt.scatter(kmeans.cluster_centers_[:, 0], kmeans.cluster_centers_[:, 1], 
           c='red', marker='x', s=200)
plt.show()
```