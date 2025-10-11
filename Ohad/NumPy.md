A [[Python]] library for fast math calculations
#machine-learning
## syntax
### Import
`import numpy as np`
### Array
```
A=np.array([[1,2,3],[4,5,6]]) // create 2x3 matrix
print(A.sum(axis=0)) // print the vertical sum

OUTPUT:
[5,7,9]

```
### A note on arrays -
using np.random.randn(a) will give us a rank 1 array with the shape (5,). this is not advisable, as it is not consistent or well understood. 

instead, we should use np.random.randn(a,1) to have a proper column vector. or randn(1,a) for a row vector. this helps us understand the behavior of the vector.


