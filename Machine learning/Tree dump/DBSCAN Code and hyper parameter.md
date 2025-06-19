```
# DBSCAN CLUSTERING - Quick Reference

# IMPORTS
from sklearn.cluster import DBSCAN
from sklearn.datasets import make_blobs
from sklearn.neighbors import NearestNeighbors
import matplotlib.pyplot as plt
import numpy as np

# BASIC USAGE
# 1. Create model with hyperparameters
dbscan = DBSCAN(
    eps=0.5,               # maximum distance between points in same cluster
    min_samples=5,         # minimum points to form a cluster
    metric='euclidean',    # distance metric
    algorithm='auto'       # algorithm for nearest neighbors
)

# 2. Fit and predict (no separate predict method!)
labels = dbscan.fit_predict(X)

# ACCESS RESULTS
core_samples = dbscan.core_sample_indices_  # indices of core points
n_clusters = len(set(labels)) - (1 if -1 in labels else 0)  # exclude noise
n_noise = list(labels).count(-1)  # noise points labeled as -1

# FIND OPTIMAL EPS - K-distance plot
def find_optimal_eps(X, k=4):
    """Find optimal eps using k-distance plot"""
    neighbors = NearestNeighbors(n_neighbors=k)
    neighbors.fit(X)
    distances, indices = neighbors.kneighbors(X)
    
    # Sort distances to k-th nearest neighbor
    k_distances = distances[:, k-1]
    k_distances = np.sort(k_distances)
    
    plt.figure(figsize=(8, 5))
    plt.plot(k_distances)
    plt.xlabel('Points sorted by distance')
    plt.ylabel(f'Distance to {k}th nearest neighbor')
    plt.title('K-distance Plot (look for elbow)')
    plt.grid(True)
    plt.show()
    
    return k_distances

# PARAMETER TUNING - Grid search approach
def tune_dbscan_params(X, eps_values, min_samples_values):
    """Try different parameter combinations"""
    results = []
    
    for eps in eps_values:
        for min_samples in min_samples_values:
            dbscan = DBSCAN(eps=eps, min_samples=min_samples)
            labels = dbscan.fit_predict(X)
            n_clusters = len(set(labels)) - (1 if -1 in labels else 0)
            n_noise = list(labels).count(-1)
            
            results.append({
                'eps': eps,
                'min_samples': min_samples,
                'n_clusters': n_clusters,
                'n_noise': n_noise,
                'noise_ratio': n_noise / len(X)
            })
    
    # Print results
    print("eps\tmin_samples\tclusters\tnoise\tnoise_ratio")
    print("-" * 50)
    for r in results:
        print(f"{r['eps']:.2f}\t{r['min_samples']}\t\t{r['n_clusters']}\t{r['n_noise']}\t{r['noise_ratio']:.2f}")

# COMPLETE EXAMPLE
# Create sample data with noise and different densities
X, _ = make_blobs(n_samples=300, centers=4, cluster_std=0.8, random_state=42)
# Add some noise points
noise = np.random.uniform(-8, 8, (50, 2))
X = np.vstack([X, noise])

# Find optimal eps
print("Finding optimal eps parameter:")
k_distances = find_optimal_eps(X, k=4)

# Apply DBSCAN
dbscan = DBSCAN(eps=1.0, min_samples=5)
labels = dbscan.fit_predict(X)

# Print results
n_clusters = len(set(labels)) - (1 if -1 in labels else 0)
n_noise = list(labels).count(-1)
print(f"\nClusters found: {n_clusters}")
print(f"Noise points: {n_noise}")

# Plot results
plt.figure(figsize=(10, 6))
unique_labels = set(labels)
colors = plt.cm.Spectral(np.linspace(0, 1, len(unique_labels)))

for k, col in zip(unique_labels, colors):
    if k == -1:
        # Black for noise points
        col = 'black'
    
    class_member_mask = (labels == k)
    xy = X[class_member_mask]
    
    if k == -1:
        plt.scatter(xy[:, 0], xy[:, 1], c=[col], marker='x', s=50, alpha=0.6, label='Noise')
    else:
        plt.scatter(xy[:, 0], xy[:, 1], c=[col], s=50, alpha=0.8, label=f'Cluster {k}')

plt.title('DBSCAN Clustering')
plt.xlabel('Feature 1')
plt.ylabel('Feature 2')
plt.legend()
plt.show()

# Parameter tuning example
print("\nParameter tuning:")
eps_values = [0.5, 0.8, 1.0, 1.2, 1.5]
min_samples_values = [3, 5, 7, 10]
tune_dbscan_params(X, eps_values, min_samples_values)```