---
aliases: 
creation date: Friday, April 22nd 2022, 6:28 pm
date updated: Sunday, September 4th 2022, 5:07 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
- '#status/🚧'
---

# [[Strang 16. Least squares approximations]]
[[18.06 Linear Algebra Strang]]


woohoo it is here

## Properties of Projection

Reiteration of projection: 
Projection matrix: $A(A'A)\inv A$
If $b$ is in the column space of $A$ then $Pb = b$, and therefore $P = I$. If $b \perp C(A)$ then $Pb = 0$.: 
$b \perp C(A) \to b \in N(A')$, so $(A'A)\inv A'b$ = (A'A)\inv (0) = 0$. 

Column space is $Ax$ for some $x$. So if $b \in C(A)$ then $Pb = A(A'A)A' b = A(A'A)\inv A' (Ax)$ = $A [ (A'A) \inv A'A)] x = Ax = b$. 


We can also think of this as a decomposition of $b$ into $p + e$. This makes it clear that $e$ is also a projection, in this case onto the left nullspace of $A$. This projection matrix is simply $I - P$ <font color=#F7B801>which we call the annihilator matrix.</font>

## Least Squares
find the best line thru some points. This is a system of linear equations, generally with no solutions. 

Ex: points are $(1,1)$, $(2,2)$, $(3,2)$. Then the system of equations is 
$$\begin{align}
C + D &=1 \\
C + 2D &= 2 \\
C + 3D &= 2 \\
\end{align}$$
The lack of solution is apparent. 
In matrix notation: 
$$ Ax = b \to \begin{bmatrix} 1 & 1 \\ 1 & 2 \\ 1 & 3\end{bmatrix}\begin{bmatrix} C\\D\end{bmatrix} = \begin{bmatrix} 1\\2\\2\end{bmatrix}$$


But we can instead use our approximation tool:

$$\begin{align}
x &= (A'A)\inv A'b \\
A'Ax &= A'b \\
\begin{bmatrix} 1 & 1 & 1\\
1 & 2 & 3 \end{bmatrix}
\begin{bmatrix} 1 & 1 \\ 1 & 2 \\ 1 & 3\end{bmatrix}\begin{bmatrix} C \\ D \end{bmatrix} &= 
\begin{bmatrix} 1 & 1 & 1 \\ 1& 2& 3 \\ \end{bmatrix} \begin{bmatrix} 1\\2\\2\end{bmatrix} \\
\begin{bmatrix} 3 & 6 \\ 6& 14\end{bmatrix} \begin{bmatrix} C \\ D \end{bmatrix} &= 
\begin{bmatrix} 6 \\14\end{bmatrix} \\
\begin{bmatrix} 3C + 6D \\ 6C + 14D\end{bmatrix} &= 
\begin{bmatrix} 5 \\11\end{bmatrix} \\
\end{align}$$
Using Gauss Jordan:
$$ \begin{bmatrix} 
3 & 6 &|& 5 \\
6 & 14 &|& 11 \\
\end{bmatrix}$$
$$ \begin{bmatrix} 
3 & 6 &|& 5 \\
0 & 1 &|& 1/2 \\
\end{bmatrix}$$
$$ \begin{bmatrix} 
1 & 0 &|& 2/3 \\
0 & 1 &|& 1/2 \\
\end{bmatrix}$$
