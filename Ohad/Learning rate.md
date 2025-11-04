Too low -  too slow.
Too high - overshoot minima

there is no analytical way of finding optimal learning rate. it depends on the data. 

$1.0 < learningrate < 10^{-6}$

## Basic Dynamic methods
1. Momentum method. 
	each update takes into account the previous iterations gradient, using a Velocity. like ice skating. 
	without momentum (normal update)
	$w_{t+1}=w_{t}-\eta \nabla f(w_{t})$
	with momentum:efr
	$v_{t+1}=\rho v_{t}+\nabla f(w_{t})$
	$w_{t+1}=w_{t}-\eta v_{t+1}$
	the magic happens as $v$ is a function of past change, practically allow acceleration. 
2. Nesterov momentum
	instead of using past information (previous gradients), we will calculate the gradient or the future point we'll land on.
3. Time-based decay
	change the learning rate itself. 
	$learningrate=\rho_{0}{\frac{1}{1+kt}}$
## Adaptive learning rate
goal: create learning rate per weight and without relying on [[Hyperparameters]].
1. Adagrad
	big local weight change -> smaller future changes.
	small local weight change -> bigger future changes.
	creates vanishing gradients problem.
2. Adadelta
	wants to solve adagrad's problem of vanishing gradients.
3. RMSprop
4. ADAM
	improvement of RMSprop. go-to.
5. NADAM
What to use
sgd+moment and adam are a good step
use default params for adam
learning rate decay is always good

