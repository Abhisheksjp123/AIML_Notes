#### a. Simple Linear Regression
Starting with 1 independent variable(, how to decide which line the best?
![[638858070829389524.png]]
We take a reference line which is horizontal line passing through the mean of y axis data  
and we test how good fit in the line by taking Sum of Squared residuals , And rotate the line and Calculate the Same for them Such that we reach the sweet spot of the lowest least Square  
this is Called **Ordinary least square method(OLS)** to optimize best fit.
![[638858073177430239.png]]
we can take derivative of fit of Sum of least squares and equate it to find best fit line. Both slope and intercept need to be optimized (usually done by Computers )
![[638858073458582135.png]]

Main idea to create a linear regression model is to:  
1) use least square to fit a line to the data  
2) Calculate [[R Square]]
3) Calculate [[P Value]] of [[R Square]]
  
let's say modelling mouses weight to determine mouse height. we fit a line though least Square method and come up with equation  
Y= 0.1+ 0.7 X  
  
Now how to determine accuracy aka how good is this Equation , for this we Calculate [[R Square]]  
[[R Square]] tells us how much of the total variance is explained by best fitted line with weight , another perspective to this is how well is weight able to explain height ( for variable selection )

#### b. Multiple Linear Regression
But What happens if we have more than one independent Variable
example
![[638858075413009880.png]]

Note as the equation will now be like:
Y= 0.1 +0.7x+ 0.3z  
And with the introduction of every new variable ( lets say we take flipping a Coin which has no direct relation with mouse size) will not harm the equation as if the Variable is making the fit worse it coefficient will go 0 .
Now, but due to random chance there might a probability that the small Mice in the data Set gets more head, this will introduce a coefficient and Improve RSq which is a false impression of a better model.
Because of this people use  [[Adjusted R Square]] which is [[R Square]] scaled with number of parameters  



#### c. [[Polynomial Linear Regression]]

#### d. How to determine [[Statistical significance of R Square by F-statistic test]]

