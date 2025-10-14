a mechanism which allows [[NumPy]] to perform pair-wise operations between two differently shaped [[Matrix]].
## example
We want to add these two matrices:
$\begin{bmatrix}1 & 2 & 3 \\ 4 & 5 & 6\end{bmatrix}+\begin{bmatrix}2 \\ 2 \\ 2\end{bmatrix}$ 
but we can't add a a $(2,3)$ matrix with a $(2,1)$ matrix
so python essentially broadcasts the $(2,1)$ matrix such that is effectively becomes (without explicit calculating) 
$\begin{bmatrix}1 & 2 & 3 \\ 4 & 5 & 6\end{bmatrix}+\begin{bmatrix}2 & 2 & 2 \\ 2 & 2 & 2\end{bmatrix} = \begin{bmatrix}3 & 4 & 5 \\ 6 & 7 & 8\end{bmatrix}$ 

note that python can only broadcast one of the elements and not both, so adding a (2,3) matrix with a (1,2) matrix is not possible and causes an error.
## Syntax:
![[Pasted image 20251010103902.png]]



