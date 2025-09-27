#Probability #math #ml #machine-learning #swag #sigmoid #linear-regression #logistic-regression #cost-function #loss-function

unlike [[linear regression]], logistic regression is for binary classifications. and instead of fitting a curve, we fit an S shaped graph that goes from 0 to 1.

uses [[maximum likelihood]] to find the best fitting S curve
### Parameters and variables
Given $X\in \mathbb{R^nxn}$ a sample set. 
we want to find a $\hat{y}=P(y=1|X)$
$\hat{y}$ is the predicted value. $y$ is the actual value. 
in this case, $y\in{\{ 0,1 \}}$ 

If we simply fit a line through the data, using linear regression, we get
$\hat{y}=W^TX+b$  
$W\in \mathbb{R}^{n_{x}}$ is the set of weights we learn
$b\in \mathbb{R}$ is the bias we learn

but $-\infty < W^TX +b < \infty$ and we want a probability. 

so we apply the [[Sigmoid]] function
and now we have our output $\hat{y}=\sigma(P(y=1|X)$
which is a valid probability: $0\leq\hat{y}=\sigma(P(y=1|X))\leq1$

[[Loss function]]

[[Cost function]]