---
aliases: 
creation date: Tuesday, April 26th 2022, 9:21 pm
date updated: Sunday, September 4th 2022, 6:00 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 17. Gram-Schmidt and A = QR]]

[[18.06 Linear Algebra Strang]]


Let's have a set of vectors - called $q_i$. We can call them orthonormal if $||q_i|| = 1$, and 
$q_i'q_j = 1$ if $i = j$ and $0$ otherwise. 

Why is this helpful?

Consider $Q = \begin{bmatrix} q_1, q_2 \ldots q_n \end{bmatrix}$. We can have $Q'Q$ very easily; the daigonal is the lengths of the $q_i$, and the off-diagonals are $0$. But the lengths of the $q_i$ are $1$, so $Q'Q = I$.

$Q$ is a new type of matrix: a matrix with orthonormal columns. 

Definitions note: $Q$ can only be called an "orthogonal" matrix if it's square also. 

If $Q$ is square and $Q'Q = I$ then $Q\inv = Q'$
