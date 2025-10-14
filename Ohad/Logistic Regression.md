#Probability #math #ml #machine-learning #swag #sigmoid #linear-regression #logistic-regression #cost-function #loss-function

unlike [[Linear Regression]], logistic regression is for binary classifications. and instead of fitting a curve, we fit an S shaped graph that goes from 0 to 1.

uses [[Maximum Likelihood]] to find the best fitting S curve
### Parameters and variables
Given $X\in \mathbb{R^nxn}$ a sample set. 
we want to find a $\hat{y}=P(y=1|X)$
$\hat{y}$ is the predicted value. $y$ is the actual value. 
in this case, $y\in{\{ 0,1 \}}$ 

If we simply fit a line through the data, using linear regression, we get
$\hat{y}=W^TX+b$  // [[Dot Product]]
$W\in \mathbb{R}^{n_{x}}$ is the set of weights we learn
$b\in \mathbb{R}$ is the bias we learn

but $-\infty < W^TX +b < \infty$ and we want a probability. 

so we apply the [[Sigmoid]] function
and now we have our output $\hat{y}=\sigma(P(y=1|X)$
which is a valid probability: $0\leq\hat{y}=\sigma(P(y=1|X))\leq1$

This basically means that
if $y=1$ then $P(Y|X)=\hat{y}$
if $y=0$ then $P(Y|X)=1-\hat{y}$

or in other words, if the image is a cat, the probability given by our model would be $\hat{y}$. if its not a cat, the probability of our model would be $1-\hat{y}$

these two equations can be summarized as:
$P(Y|X)=\hat{y}^y(1-\hat{y})^{(1-y)}$
also called the Bernoulli likelihood
because if $y=1$ then $\hat{y}^1(1-\hat{y})^{0}=\hat{y}$
and if $y=0$ then $\hat{y}^0(1-\hat{y})^1=1-\hat{y}$


[[Loss Function]]

[[Cost Function]]

### Implementing of [[Logistic Regression]] using [[Gradient Descent]]:
![[Pasted image 20251009190346.png]]

importantly we get that $dZ=a-y$ 
and $dW_{1}=X_{1}*dZ$, $dW_{2}=X_{2}*dZ$, $db=dZ$

#### Code:
for iter in range(1000):
	Z=np.dot(W.T,X)+b //compute score of all m examples
	A=sigmoid(Z) //apply sigmoid on all scores
	dZ=A-Y // deriviative of loss wrt Z is prediction minus label
	dW=$\frac{1}{m}$np.dot(X,Z.T) // average gradient for best loss 
	db=$\frac{1}{m}$np.sum(dZ) // find average of residuals
	W=W-$\alpha dW$ // update weights
	b=b-$\alpha db$ //update bias

Speed-ups are possible with [[Vectorization]], [[Python Broadcasting]], etc..