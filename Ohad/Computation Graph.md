Example:
say we want to compute a [[Cost Function]] such as
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
if $A=5+\epsilon \implies V=A+3\epsilon$ 
in other words, a small bump in $A$ causes a 3 fold bump in $V$

In summary, changing $A$ would change $V$, and changing $V$ would change $J$. so the net change in $J$ for a small change in $A$ is $3*3=9$. also known as the [[Chain Rule]].

FinalOutputVariable = J, the last node in the [[Computation Graph]].

many computations end up being:
$\frac{dFinalOutputVariable}{dVar}$ = $\frac{dJ}{dVar}$
which is also called $dV$


So in essence, to compute the deriviatives of the input variables $(A,B,C)$ in $J(A,B,C)$ it is more efficient to start with $\frac{dJ}{dV}$ which will be useful for calculating $\frac{dV}{dA}$ and $\frac{dV}{dU}$ and they will be used to calculate $dA=\frac{dJ}{dA}=\frac{dJ}{dV}*\frac{dV}{dA}$ and so on for $B,C$.