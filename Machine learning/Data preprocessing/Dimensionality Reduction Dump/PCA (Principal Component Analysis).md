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
Here is a reddit person answer to it, ans why i should not stress about its derivation:
OP:
That's a professor of a masters degree level class saying something to the effect of: "I'm not going to abuse you with the mathematical derivation of PCA because that would take an entire semester".

Principal components analysis is useful because it converts a 50 dimensional space into an smaller: maybe 8 or 3 dimensional space with the same representative variance. Reduce dimensionality without reducing information contained in it.

For an ELI5, Imagine you have a pencil, the pencil has height width and depth, you can roll it in your hands, the axis of rotation is the "direction of maximum variance", if I rebase the representation coordinate plane to one, along that axis of rotation, I can reduce your 3 dimensional pencil to a 1 dimensional pencil where every particle of the pencil is just a number on a single dimension, for example: [1, 2, 4, 5, 8, 9, 10, ...]

The three dimensional pencil has been reduced in dimension to 1, while most of the variance has been preserved. The last 4 pages is trying to explain that mathematically.

If you hunker down and try to understand Eigenvalues and Eigenvectors, some pieces of that begin to make sense. PCA operates by finding the EigenVector, the direction of maximum variance. Some helpful links:

[https://www.youtube.com/watch?v=PFDu9oVAE-g](https://www.youtube.com/watch?v=PFDu9oVAE-g)

If I had to explain Eigenvectors and EigenValues in one paragraph it's this:

The constant vector value and multiple value that make this equation correct: (numpy.dot(MATRIX, vector) == scalar_multiple * vector). It's useful because discovering how a Matrix times a vector produces the same result as a scalar times a vector is important for finding the axis of rotation of this matrix multiplication. You've eliminated a dimension while not reducing any of the data contained in it.

More words:

Eigenvectors are the methodology that pca uses to find the new basis vector for the coordinate plane. So you must understand this. Imagine we have two input features. Tire age and tire wear. We plot these on a scatterplot and it makes a diagonal straight line.

We want to reduce these two features to one feature since the data is so plain, we can compress the two dimensional object to 1. So if we find the eigenvector, that is the axis of rotation, imagine taking a pencil and rolling it between your palms, it spins along its axis of rotation. The eigenvector is that vector of axis of rotation of minimum variance.

Reset the scatterplot points along this new line. And you have a recipe for compressing a 2 dimension object to one, while preserving all of the information contained in the 2d object.

If i take a basketball and spin it. There will be two spots on the ball that i can touch while it spins. Those two points are the eigenvector. The basketball spinning is like the transformation matrix continually transforming the Cartesian plane.

the "WTF" feeling you get is not a result of defection here or someone blowing smoke or throwing sand in your eyes. This is legit machine learning, the thing your brain does when it dismisses petabytes of irrelevant information and tracks in instantaneously toward (distilling) huge data into the single feature (hinge) that reliably determines the outcome of the whole system. It is WTF and hard, break into it anyway like crashed alien technology found dug up on Mars, the gratification for figuring it all out and seeing implications for how a machine might use these ideas to outperform humans on all tasks is orgasmic, it's like creating a component of silicon based life forms without having sex.

If it was easy, you wouldn't be working on it because people orders of magnitude smarter than you would have figured it out decades ago and hidden it behind locked doors.

What you need is a formal education in higher math, I suggest you take this class: Discrete mathematics. If you're not up to that, then read chapters 1 and 2, every paragraph of [http://de36ce.com/wp/wp-content/uploads/2015/09/Rosen_Discrete_Mathematics_and_Its_Applications_7th_Edition.pdf](http://de36ce.com/wp/wp-content/uploads/2015/09/Rosen_Discrete_Mathematics_and_Its_Applications_7th_Edition.pdf) . For example in explaining what the implications of that mysterious double-struck R means in the first sentence. If you didn't already know what that glyph means by reading the prerequisite material, anyone would be lost being exposed to it when used in a sentence.

