---
aliases: 
creation date: Tuesday, April 26th 2022, 9:21 pm
date updated: Sunday, September 4th 2022, 6:23 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 17. Gram-Schmidt and A = QR]]

[[18.06 Linear Algebra Strang]]

## Matrices with Orthonormal Columns

Let's have a set of vectors - called $q_i$. We can call them orthonormal if $||q_i|| = 1$, and 
$q_i'q_j = 1$ if $i = j$ and $0$ otherwise. 

Why is this helpful?

Consider $Q = \begin{bmatrix} q_1, q_2 \ldots q_n \end{bmatrix}$. We can have $Q'Q$ very easily; the daigonal is the lengths of the $q_i$, and the off-diagonals are $0$. But the lengths of the $q_i$ are $1$, so $Q'Q = I$.

$Q$ is a new type of matrix: a matrix with orthonormal columns. 

Definitions note: $Q$ can only be called an "orthogonal" matrix if it's square also. 

If $Q$ is square and $Q'Q = I$ then $Q\inv = Q'$. 

Any projection matrix is a $Q$. Another kind is a Hadamard matrix, which has orthonormal columns, is square, and consists only of $1$ and $-1$. 


## Applications

OK so what is the point of this circus

Suppose $Q$ has orthonormal columns, and I want to project onto the column space. Then $P = Q(Q'Q)\inv Q'$. But $Q'Q = I$, so we are left with $P = QQ'$. (If $Q$ is square, then $P = I$, because the columns of $Q$ are a basis for the space).

So projection is very simple. 

The normal equation, $A'A = A'b$, becoms $Q'Q \hat x = Q'b$, or $x = Q'b$. So each $x_i$ is $q_i'b$. 

This is cool! It becomes even cooler, though, when I can take any set of independent vectors and *make* them into orthonormal vectors, so I can do the same sort of projection tricks. 

This is the point of the Gram-Schmidt process. 

Say we have three independent vectors $a,b,c$. 
We pick one to start with, $a$. So we want to then get the part of $b$ that's orthogonal to $a$. So we can have $(I-P)b = b - \dfrac{A'b}{A'A}A$. 
Then we can make $c$: 
$c - \frac{A'c}{A'A}A - \frac{B'c}{B'B}B$. Now $c$ is orthogonal.

You can just divide each by its length to make them all unit vectors. 

NOTE: the column space of the new $Q$ is the same as that of $A$! That's because we kept the same basis. 

We can then define a new decomposition, $A = QR$. 

#status/section/🚧 
