In statistics, data science and machine learning, we optimize a lot of stuff. when we fitted a line in linear regression we optimized the slope, we optimized the swigley while fitting logistic regression , and when we run t-SNE We optimize clusters. The Cool thing is Gradient descent can optimize these things and much more.

Step by step process to optimize slope and intercept in Linear Regression with GD
let's start with optimizing the intercept and keep slope = 0.64  
Predicted height = intercept +0.64 x Weight

step1) take a random initial value for intercept =o , this will give GD a starting point for Something to improve upon  
step2) Now we will take a loss function to optimize upon, In this Case it is Sum Squared residual
$$
Loss/Cost function = SSR = (Hi - (C + 0.64*Wi))^2
$$
Step 3)NOTE: If we were using Least Squares to Solve for the optimal value for the Intercept, we would  
simply find where the the slope of the curve = 0.In contrast, Gradient Descent finds the minimum value by taking steps from an initial guess until it reaches the best value.This makes Gradient Descent very useful when it is not possible to solve for where the derivative = o, and this is why Gradient Descent can be used in so many different situations.

![[638858091441499456.png]]
Step 4) Now we'll change intercept and the step we'll use to reduce intercept is determined by step size , this is determined by gradient descent  
when Slope is far from zero we'll take Small Steps , and when close to O Small Steps  
Gradient descent decides the intercept by multiplying Slope by learning rate  
Step size = Slope x learning rate  
Intercept new = intercept old - step size
![[638858091864386427.png]]In the above example of GD Slope Converges to o and we get optimal intersept after 6th step

Step 6) but how do we decide how much steps GD must take to get to the optimal solution?  
a) when the step size is very close to O (in practice 0-001 or smaller )  
b) or there is no of steps defined before it gives up ( in practice max steps = 1000 )

NOW let's talk abut how to estimate the Intercept and the Slope.Just like before, we will use the Sum of the Squared Residuals as the Loss Function. This iS a 3-D graph of the Loss Function for different values for the Intercept and the Slope.
![[638858092967576418.png]]
This time again we'll also take derivative of loss function with intercept to find optimal intercept, but unlike before, we'll also take the derivative with respect to the Slope.

![[638858093284621957.png]]

NOTE: When you have two or more derivatives of the same function, they are called a Gradient.We will use this Gradient to descend to lowest point in the Loss Function, which, in this case, is the Sum of the Squared Residuals. This is why the algorithm is Called gradient descent.  
  
Step 1) This time with Intercept = 0 and Slope = 1, is where we will start.  
and rest of the things follows Same route


Also Read:
[[Stochastic Gradient descent]]