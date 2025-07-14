In our example, we only had three data points, so the math didn't take very long, but when you have millions of data points, it can take a long time.  
This is where Stochastic Gradient descent Comes handy. Stochastic Gradient Descent would randomly pick one sample for each step and just use that one sample to calculate the derivatives.  
  
NOTE: The strict definition of Stochastic Gradient Descent is to only use 1 sample per step however, it is more common to select a small subset of data or mini-batch, for each step.