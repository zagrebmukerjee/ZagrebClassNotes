---
date updated: 2022-04-22 18:27

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
- '#status/🚧'
---

## Vector Spaces

Continuation of discussion from [[Strang 5. Transposes, Permutations, Vector Spaces#Vector Spaces and Subspaces]]


Note that if $P$ and $L$ are subspaces, then $P \cup L$ is not necessarily a subspace, but $P \cap L$ is. Proof: If $v,w$ are in $P$, then they are in $L$. Then (since $P$ and $L$ are subspaces) it follows that $av + bw$ are in $P$, and that $av + bw$ are in $L$, meaning $av + bw$ are in $P \cap L$.

## Column Spaces

Now we are moving on to vector spaces associated with a particular matrix. 

The <font color=gree>Column Space</font> of a matrix is the space that is made up of all linear combinations of its columns. So, imagine:

$$A = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 1 & 3 \\ 3& 1 & 4\\ 4& 1 & 5\end{bmatrix}$$
Each column is a vector in $\R^4$. So the column space of $A$ is a subspace of $\R^4$. We can call it $C(A)$. Because there are three columns, we can say this space is in fact a subspace of $\R^3$. 

Does $Ax = b$ have unique solutions for all $b$? 

$$Ax = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 1 & 3 \\ 3&1 & 4\\ 4 & 1 & 5 \end{bmatrix}\begin{bmatrix} x_1 \\ x_2 \\x_3 \end{bmatrix} = \begin{bmatrix} b_1 \\ b_2 \\ b_3 \\b_4\end{bmatrix}$$

This gives us 
$$\begin{aligned} 
x_1 + x_2 + 2x_3 &= b_1 \\
2x_1 + x_2 + 3x_3 &= b_2 \\
3x_1 + x_2 + 4x_3 &= b_3 \\
4x_1 + x_2 + 5x_3 &= b_4 \\
\end{aligned}
$$
This has too many equations. Already we can sense trouble. 