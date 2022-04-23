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
We can conceptualize this as linear combinations of columns of $A$: 
$$Ax = x_1\begin{bmatrix} 1\\2\\3\\4\end{bmatrix} + x_2 \begin{bmatrix} 1 \\1 \\1 \\1\end{bmatrix} + x_3 \begin{bmatrix} 2\\3\\4\\5\end{bmatrix}= \begin{bmatrix} b_1 \\ b_2 \\ b_3 \\b_4\end{bmatrix}$$

We want $b$ that are linear combinations of the columns of $A$ - the column space of $A$. There are many $b$ we can't get - this is like saying that $C(A) \subset \R^4$. 

The columns of $A$ are linearly dependent, causing problems. We will later discover that columns 1 and 2 are the <font color=gree>pivot columns</font> of $A$, meaning that throwing out column $3$ does nothing to the column space (we could say the same for column $1$ - by convention, we go left to right).


## Null Space

Let's have the same $A$ as before. 

 
$$Ax = x_1\begin{bmatrix} 1\\2\\3\\4\end{bmatrix} + x_2 \begin{bmatrix} 1 \\1 \\1 \\1\end{bmatrix} + x_3 \begin{bmatrix} 2\\3\\4\\5\end{bmatrix}= \begin{bmatrix} b_1 \\ b_2 \\ b_3 \\b_4\end{bmatrix}$$
We can solve this for e.g. $b = 0$ easily. Too easily, it turns out. $x_1 = x_2 = 1, x_3 = -1$ works. But so does $x_1 = x_2 =2, x_3 = -2$. Matrix $A$ sends that whole plane $x_1 + x_2 - x_3 = 0$ to $0$ (Incidentally, meaning $A$ is singular). 

This means the <font color=gree>null space</font> of $A$ is the plane above.  