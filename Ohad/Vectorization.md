The skill of replacing a [[For Loop]] with a vector operation (like [[Dot Product]]). this is used to speed up calculations such as [[Back Propogration]], since [[For Loop]]s are slow as they are sequential and custom commands such as [[Dot Product]] in [[NumPy]] can use parallel computation and less overhead.

$Z=W^TX+b$
where $X$ and $W\in R^n$

non-vectorized:
$Z=0$
for i in range(n-x)
	$Z+=W_{i}*X_{i}$
$Z+=b$

vectorizerd:
$Z=np$ * dot($W,X$)+b

