A mathematical structure.
For example A is a (2,3) Matrix, meaning it has 2 rows and 3 columns.
$A_{(2,3)}=\begin{bmatrix}1 & 1  3 & 7 \\ 8 & 9 & 67\end{bmatrix}$

We can look at a system of equations such as
$x+2y+z=2$
$3x+8y+z=12$
$4y+z=2$
as 
$Ax=b$
where
$A = \begin{bmatrix}1 & 2 &1 \\ 3 & 8 & 1 \\ 0 & 4 & 1\end{bmatrix}$
$x=\begin{bmatrix}x\\y\\z\end{bmatrix}$
$b=\begin{bmatrix}2\\12\\2\end{bmatrix}$
## Matrix Elimination
Lets choose the first pivot and knock out the x's in the second equation

$A = \begin{bmatrix}[1] & 2 &1 \\ 3 & 8 & 1 \\ 0 & 4 & 1\end{bmatrix} \to R_{2}=3R_{1}-R_{2}\to$ 
$\begin{bmatrix}1&2&1 \\0 & [-2] & 2 \\ 0 & 4 & 1\end{bmatrix} \to R_{3}=2R_{2}-R_{3}\to$
$\begin{bmatrix}1&2&1 \\0 & -2 & 2 \\ 0 & 0 & 3\end{bmatrix}$
but how did the transformations affect b?
$\begin{bmatrix}2\ \\ 3*2-12 \\ 2*(3*2-12)-2\end{bmatrix}=\begin{bmatrix}2 \\ -6\\ -14\end{bmatrix}$
## Back Substitution
using matrix elimination we know $3z=-14$
extract z and solve for y etc etc.
