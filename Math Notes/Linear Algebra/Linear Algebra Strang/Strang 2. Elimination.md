---
date updated: 2022-03-21 13:23

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes/math/linalg'
---

# [[Strang 2. Elimination]]

- How to solve systems of equations? Turn it into an augmented matrix and eliminate.  
- Want to do elementary row operations until you have an upper-triangular matrix. Then can 'back-substitute'

Recall ex. from last lecture: 

$$\begin{aligned}
2x - y   &= 0 \\
-x + 2y  -z &= -1 \\
 - 3y  -4z &= 4 \\
\end{aligned}$$
In augmented matrix form, this is:

$$
\begin{bmatrix}
2 & -1 & 0 &|& 0 \\
-1 & 2 & -1 &|& -1 \\
0 & -3 & -4 &|& 4 \\
\end{bmatrix}
$$
Add half the first row to the second; then add twice the new second row to the third. 
$$
\begin{bmatrix}
2 & -1 & 0 &|& 0 \\
0 & 3/2 & -1 &|& -1 \\
0 & 0 & -6 &|& 2 \\
\end{bmatrix}
$$

- The diagonal elements of the reduced matrix are 'pivots'. Determinants are product of pivots
- The pivots can't be zero. If they are forced to be, and you can't fix it through exchanging or adding rows, then system is unsolvable $\iff$ matrix is singular

- Suppose $A$ is a matrix and $U$ is the upper-triangular matrix resulting from elimination. Let $E_1$ be the matrix that represents the first step of elimination - i.e., if elimination has $n$ steps, $E_n E_{n-1} \ldots E_2 E_1 A = u$. 
- $E$ is the product of those elimination matrices. 
