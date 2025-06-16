**Definition:** Performance degrades as number of features increases

## Core Problem

- High dimensions → all data points become equally distant
- Algorithms can't distinguish between "close" and "far" points
- Need exponentially more data to fill the space

## Why It Happens

- **Volume concentration:** In high dimensions, most space is empty
- **Sparsity:** Data points spread too thin across dimensions
- **Distance breakdown:** Everything becomes roughly same distance apart

## Affected Algorithms

- **k-NN:** Can't find meaningful neighbors
- **Clustering:** Clusters become meaningless
- **SVM:** Distance calculations fail
- **Most ML models:** Overfitting increases

## Real Examples

- **Text:** Documents with 10,000+ word features
- **Genomics:** 20,000+ genes, few samples
- **Images:** Raw pixels create huge feature space

## Solutions

**Reduce dimensions:**

- PCA, t-SNE, autoencoders

**Select features:**

- Remove irrelevant variables
- Use domain knowledge

**Regularize:**

- L1/L2 penalties to prevent overfitting

**Change algorithms:**

- Use methods robust to high dimensions

## Key Takeaway

More features ≠ better performance. Often fewer, good features > many noisy features.