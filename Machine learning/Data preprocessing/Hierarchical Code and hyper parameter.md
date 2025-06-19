```
# HIERARCHICAL CLUSTERING - Quick Reference

# IMPORTS
from sklearn.cluster import AgglomerativeClustering
from scipy.cluster.hierarchy import dendrogram, linkage
from sklearn.datasets import make_blobs
import matplotlib.pyplot as plt
import numpy as np

# BASIC USAGE
# 1. Create model with hyperparameters
hierarchical = AgglomerativeClustering(
    n_clusters=3,           # number of final clusters (can be None)
    linkage='ward',         # linkage criterion
    distance_threshold=None, # alternative to n_clusters
    metric='euclidean'      # distance metric
)

# 2. Fit and predict (no separate predict method!)
labels = hierarchical.fit_predict(X)

# ACCESS RESULTS
n_clusters = hierarchical.n_clusters_
n_leaves = hierarchical.n_leaves_

# DENDROGRAM - Visualize hierarchy
def plot_dendrogram(X, method='ward'):
    linkage_matrix = linkage(X, method=method)
    plt.figure(figsize=(10, 6))
    dendrogram(linkage_matrix)
    plt.title('Hierarchical Clustering Dendrogram')
    plt.xlabel('Sample Index')
    plt.ylabel('Distance')
    plt.show()
    return linkage_matrix

# FIND OPTIMAL CLUSTERS - Using distance threshold
def find_optimal_clusters(X, max_distance=10):
    distances = []
    cluster_counts = []
    
    for threshold in np.linspace(0.5, max_distance, 20):
        hierarchical = AgglomerativeClustering(
            n_clusters=None,
            distance_threshold=threshold,
            linkage='ward'
        )
        labels = hierarchical.fit_predict(X)
        distances.append(threshold)
        cluster_counts.append(hierarchical.n_clusters_)
    
    plt.plot(distances, cluster_counts, 'bo-')
    plt.xlabel('Distance Threshold')
    plt.ylabel('Number of Clusters')
    plt.title('Clusters vs Distance Threshold')
    plt.show()

# COMPLETE EXAMPLE
X, _ = make_blobs(n_samples=300, centers=4, random_state=42)

# Plot dendrogram to choose clusters
plot_dendrogram(X)

# Apply hierarchical clustering
hierarchical = AgglomerativeClustering(n_clusters=4, linkage='ward')
labels = hierarchical.fit_predict(X)

# Plot results
plt.scatter(X[:, 0], X[:, 1], c=labels, cmap='viridis')
plt.title('Hierarchical Clustering Results')
plt.show()

# Alternative: Use distance threshold instead of fixed clusters
hierarchical_auto = AgglomerativeClustering(
    n_clusters=None, 
    distance_threshold=5,
    linkage='ward'
)
labels_auto = hierarchical_auto.fit_predict(X)
print(f"Auto clusters found: {hierarchical_auto.n_clusters_}")
```