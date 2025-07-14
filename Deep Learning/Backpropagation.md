Backpropagation is a simple concept with [[Gradient descent]] with main idea.
1. Using the [[Chain rule]] to calculate derivatives  
2. Plugging derivatives into gradient descent to optimize parameters

Lets take an example to understand, we'll name all the parameters for easier understanding
![[638866525508849522.png]]
Note* : Conceptually back propagation Starts with the last Parameter b3 and work backward to estimate all other parameter. However, we can discuss all of the Main Ideas behind backpropagation by just estimating the last Bias i.e b3. So, in order to start from the back, let's assume that we already have optimal values for all of the parameters except for the last bias.
![[638866526548041502.png]]
So by doing the steps till b3 we get this green wiggle . Now we are ready to add the final bias such that it is provides the best possible fit
![[638866527064014041.png]]
Now as this is an optimization problem we'll use [[Gradient descent]] 
Step 1: Initialize the  value of b3 as 0
Step 2: here we'll use sum of Squared residuals (SSR) as loss function and objective is to get lowest possible Value for loss function through gradient descent
$$
Loss function = {Observed}_i - \text{Predicted}_i
$$
$$
\frac{d \text{SSR}}{d b_3} = \sum_{i=1}^{n=3} -2 \times (\text{Observed}_i - \text{Predicted}_i) + \frac{d}{d b_3}(\text{blue} + \text{orange} + b_3)
$$
$$= \sum_{i=1}^{n=3} -2 \times (\text{Observed}_i - \text{Predicted}_i) \times 1$$
Step 3: Now we've got the derivative we'll use this equation with [[Gradient descent]] given initial Value b3=0 and we get derivative= -15.7 at that.
$$\text{New Step size} = \text{Slope} \times \text{Learning rate(0.1)} = -1.57$$
new optimal value of b3
$$b_{3,\text{new}} = b_{3,\text{old}} - \text{step size} = 1.57$$


and this continues till value of slope Converges/step size is close to 0, and with that we get the optimal value of b3
