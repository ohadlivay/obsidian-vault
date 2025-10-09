Example:
say we want to compute
$J(A,B,C) =3(A+BC)$
we could say that it involved 3 computations:
$U=BC$
$V=U+A$
$J=3V$
We can turn this into a graph which looks like:
![[Pasted image 20251009183121.png]]
We can use this graph to calculate the [[Deriviative]]'s.
$\frac{dJ}{dV}$=3 because increasing $V$ by $\epsilon$ results in an increase of $3\epsilon$ in $J$. This was a single step in [[Back Propogration]]

$\frac{dJ}{dA}=3$ because  
$A=5+\epsilon \implies V=A+3\epsilon$ 
in other words, a small bump in $A$ causes a 3 fold bump in $V$

In summary, changing $A$ would change $V$, and changing $V$ would change $J$. so the net change in $J$ for a small change in $A$ is $3*3=9$. also known as the [[Chain Rule]].