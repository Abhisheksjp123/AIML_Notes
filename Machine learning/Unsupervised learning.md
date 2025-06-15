Unsupervised learning is like being a detective with a pile of clues but no case file. You have data, but no "right answers" to learn from. Your job is to find hidden patterns, structures, or relationships in the data.

Main Types of Unsupervised Learning:

### 1. [[Clustering]]

**What it does**: Groups similar data points together

### 2. [[Dimensionality Reduction]]

**What it does**: Simplifies data while keeping important information

**Why it's useful**:

- Visualization (plot 100-dimensional data in 2D)
- Remove noise and redundancy
- Speed up other algorithms

**Real-world example**: A company has customer data with 50 features (age, income, purchase history, etc.). Dimensionality reduction might reveal that most variation comes from just 3 underlying factors: "spending power," "tech-savviness," and "brand loyalty."

**Common algorithms**:

- **PCA (Principal Component Analysis)**: Finds the most important directions in data
- **t-SNE**: Great for visualization, preserves local neighborhoods


### 3. [[Association Rule Learning]]

**What it does**: Finds relationships between different items

**Classic example**: "People who buy bread and milk also tend to buy eggs" (market basket analysis)

**Applications**:

- Product recommendations
- Web usage patterns
- Gene expression analysis