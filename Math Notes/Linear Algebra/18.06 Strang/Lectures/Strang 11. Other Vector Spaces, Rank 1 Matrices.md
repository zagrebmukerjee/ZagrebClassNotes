---
aliases:
creation date: 2022-06-16 13:32
date updated: Thursday, June 16th 2022, 1:56 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 11. Other Vector Spaces, Rank 1 Matrices]]
[[18.06  Linear Algebra Strang]]

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

Rank $1$ matrices are very simple. Consider this $2 \times 3$ rank 1 matrix:

$$ A = \begin{bmatrix} 1 & 4 & 5 \\ c & 4c & 5c\end{bmatrix}$$
We know that $C(A),  C(A'), N(A')$ all have dimension $1$, and $N(A)$ has dimension $2$. It's obvious that $\begin{bmatrix} 1 & 4 & 5\end{bmatrix}$ is a basis of the row space, and $\begin{bmatrix} 1 \\ c\end{bmatrix}$ of the column space. Then we can write this matrix:

$$A = \begin{bmatrix} 1 \\ c\end{bmatrix}\begin{bmatrix} 1 & 4 & 5\end{bmatrix}$$

Rank $1$ matrices all have this form, $A = uv'$, where $u$ is a column and $v$ is a row. Can decompose any matrix into rank $1$ matrices - they are building blocks.


Are the rank $\leq 4$ matrices a subspace of the space of $5 \times 17$ matrices? No. 


Suppose we're in $\R^4$. We have some vector such that $v_1 + v_2 + v_3 + v_4 = 0$. Is this a subspace? Yes - it is a $3$ dimensional subspace. You can choose 3 variables, so the basis is something like this:

$$\left\{\begin{bmatrix} 1 \\ 0 \\ 0 \\ -1\end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 0 \\ -1\end{bmatrix}, \begin{bmatrix} 0 \\ 0 \\ 1 \\ -1\end{bmatrix} \right\} $$

This space is the null space of $A$, the solution to $Av = 0$, where $A$ is $\begin{bmatrix} 1 & 1 & 1 & 1 \end{bmatrix}$. Dimension of the column space is $1$, basis is $\begin{bmatrix} 1\end{bmatrix}$. Dimension of the row space is also $1$. Dimension of the left nullspace is $0$. 
