Feature scaling is to shrink the feature into certain common range so as to make them comparable
Two popular types of scaling:
1. [[Standardization]]
2. [[Normalization ML]]

Why Feature scaling is important?
1. ==Faster Convergence:==
Lets take example of [[Gradient descent]]
suppose we've 2 variables X1 and X2 and their coefficient thetha 1&2 which we need to optimize, (we'll keep bias term 0 for now)

$$
\theta_1 := \theta_1 - \alpha \frac{\partial J(\theta_1, \theta_2)}{\partial \theta_1}
$$$$
\theta_2 := \theta_2 - \alpha \frac{\partial J(\theta_1, \theta_2)}{\partial \theta_2}
$$
Assuming the cost function looks like this
$$J(\theta_1, \theta_2) \, = \, \frac{1}{2m} \sum(\theta_1 x_1 + \theta_2 x_2 - y)^2$$
as we've not done feature scaling lets say x1 has very small values as compared to x2,
because of this this as the time of descent
$$Small\ step\ size:\ \theta_1 \, := \, \theta_1 - \alpha \, \frac{1}{m} \sum(\theta_1 x_1 + \theta_2 x_2 - y) \, x_1
$$

$$Large\ step\ size:\\theta_2 \, := \, \theta_2 - \alpha \, \frac{1}{m} \sum(\theta_1 x_1 + \theta_2 x_2 - y) \, x_2$$

This difference b/w the step sizes will cause unwanted oscillations and delay the convergence
2. ==Computing distances approximately:==
We know that memory based algorithms like [[K-Means]] and [[K nearest neighbour]] depends on calculating distances between the data points, but what happens when the distances b/w the features is not scaled properly
lets take 2 variables which are not scaled properly, here distance from x-axis variable is more pronounced that with y-axis variable due to bigger scale
![[Screenshot 2025-06-28 at 3.10.45 AM.png]]

Lets apply Normalization
![[Screenshot 2025-06-28 at 3.12.22 AM.png]]

Now you see roughly both feature contribute equally to the distances, which makes sure algorithm will not be affected by the features scale