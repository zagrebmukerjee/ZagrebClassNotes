---
aliases:
creation date: 2022-06-16 13:32
date updated: Thursday, June 16th 2022, 1:43 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[🚧Strang 11. Other Vector Spaces, Rank 1 Matrices]]
[[18.06 Strang]]

## Matrix Vector Space

Suppose I have a space $M$ that's all $3 \times 3$ matrices. It's clearly a vector space, in that it's closed under (matrix) addition and scalar multiplication. 

It turns out this has several subspaces: upper-triangular matrices, lower-triangular matrices, diagonal matrices. 

Consider another subspace: the symmetric $3 \times 3$ matrices. What's the dimension of this space? What is a basis?
Well, how many elements can you choose in a symmetric $n \times n$ matrix: it's $n + n-1 + \ldots + 1$, or $n(n-1)/2$. In this case that's $6$: the three diagonals and the upper right three elements. So an obvious basis is: 

$$\left\{ 
\begin{bmatrix} 1 & 0 & 0 \\0 & 0 & 0 \\0 & 0 & 0\end{bmatrix},
\begin{bmatrix} 0 & 0 & 0 \\0 & 1 & 0 \\0 & 0 & 0\end{bmatrix},
\begin{bmatrix} 0 & 0 & 0 \\0 & 0 & 0 \\0 & 1 & 0\end{bmatrix},
\begin{bmatrix} 0 & 1 & 0 \\1 & 0 & 0 \\0 & 0 & 0\end{bmatrix},
\begin{bmatrix} 0 & 0 & 1 \\0 & 0 & 0 \\1 & 0 & 0\end{bmatrix},
\begin{bmatrix} 0 & 0 & 0 \\0 & 0 & 1 \\0 & 1 & 0\end{bmatrix}
\right\} $$
<font color=#F7B801>The same logic can make a basis for UT or LT matrices.</font>

So this has dimension $6$. $S \cap U$ is a subspace too, the subspace of diagonal matrices. $S + U$ is also a subspace - in fact, it is $M$, since you can make any matrix this way. So this has dimension $9$. 

In general: dim $U$ + dim $S$ = dim $U \cap S$ + dim $U + S$; in the $3 \times 3$ case, $6 + 6 = 9  + 3$. 


## Differential Equation Vector Space

Suppose we have the differential equation $\frac{d^2y}{dx^2} - y = 0$. We can solve this with $y = \cos x$ and $y = \sin x$. These are a basis for the null space of this differential equation, since the equation holds for any linear combination of them. So this space has dimension two. 


## Rank 1 Matrices 