### Loss function
measures error for a single training example

option 1: 
use [[MSE]] loss function, this will lead to us a non-[[convex optimization]] , meaning we're not guaranteed a [[global minimum]]

option 2: 
use this convex loss function: $L(\hat{y},y)=-(y\log \hat{y}+(1-y)\log(1-\hat{y})$
if $y=1$ then we try to minimize $L(\hat{y},y)=-\log \hat{y}$, so we optimize for a large $\hat{y}$
if $y=0$ then we try to minimize $L(\hat{y},y)=-\log (1-\hat{y})$, so we optimize for a small $\hat{y}$ (approach 0)