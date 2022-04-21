---
date updated: 2022-04-20 19:45

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes/math/linalg'
- '#🚧'
---

# [[Strang 4. LU Decomposition]]

We learned in [[Strang 2. Elimination|lecture 2]] about Gaussian elimination which turns a matrix $A$ into an upper-triangular matrix $U$. 

Example: 

$$A = \begin{bmatrix}2 & 1 \\ 8 & 7\end{bmatrix}$$
$$U = E_1 A = \begin{bmatrix}1 & 0 \\ -4 & 1\end{bmatrix}\begin{bmatrix}2 & 1 \\ 8 & 7\end{bmatrix} = \begin{bmatrix}2 & 1 \\ 0 & 3\end{bmatrix}$$
We can invert $E_1$ to get a lower-triangular $L$ such that $A = LU$:
$$\begin{bmatrix}2 & 1 \\ 8 & 7\end{bmatrix} = \begin{bmatrix}1 & 0 \\ 4 & 1\end{bmatrix}\begin{bmatrix}2 & 1 \\ 0 & 3\end{bmatrix}$$
Any such $E$ will be lower-triangular, and have a lower-triangular inverse. We can also pull out the pivots of $U$ to have $1$ on the diagonals:

$$\begin{bmatrix}2 & 1 \\ 8 & 7\end{bmatrix} = \begin{bmatrix}1 & 0 \\ 4 & 1\end{bmatrix}\begin{bmatrix}2 & 0 \\ 0 & 3\end{bmatrix}\begin{bmatrix}1 & 1/2 \\ 0 & 1\end{bmatrix}$$

If $A$ is $3 \times 3$ then we will have $E_{32} E_{31}E_{21} A = U$; and thus $A = E_{21}^{-1}E_{31}^{-1}E_{32}^{-1}U$. 

Why do I prefer $L$ to $E_{32} E_{31}E_{21}$? Consider: 

$$ E_{32} E_{21} = E = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & -5 & 1 \end{bmatrix}\begin{bmatrix} 1 & 0 & 0 \\ -2 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix} = \begin{bmatrix} 1 & 0 & 0 \\ -2 & 1 & 0 \\ 10 & -5 & 1 \end{bmatrix}$$
That lower left term of $E$ represents the composition of two steps - adding $-5$ times the new row $2$, which is thhe same as  $-5$ times the old row 2 + $(-2)(-5)$ times the old row $1$. 

The inverse: 
$$ E_{21}^{-1}E_{32}^{-1} = L = \begin{bmatrix} 1 & 0 & 0 \\ 2 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 5 & 1 \end{bmatrix}=\begin{bmatrix} 1 & 0 & 0 \\ 2 & 1 & 0 \\ 0 & 5 & 1 \end{bmatrix}$$
Doing this in reverse order gets rid of the ugly composite elements and lets us just see the elimination steps. 