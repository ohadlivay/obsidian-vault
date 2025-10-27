
Open source library for [[Python]] ML/DL. it has great [documentation](https://docs.pytorch.org/docs/stable/index.html) 

### Tensor
n-dimensional array, but has more support for GPU's. can be scalar, vectors, [[Matrix|matrices]] etc.
rank = dimension.
rank 0 is a scalar
rank 1 is an array
rank 2 is a matrix
and so on and so forth..

slicing works by reference and does not create new object.
can also reference using 

#### Syntax
A=torch.tesnor(3)
B

###  nn.Linear()
represents a single layer. it has inputs, outputs, weights, bias.

### Syntax
l1 = torch.nn.Linear(in_features, out_features, bias=True)

### nn.Sequential()
can chain [[Inner Layer|layers]] and add [[Activation function]]s.

Forward function