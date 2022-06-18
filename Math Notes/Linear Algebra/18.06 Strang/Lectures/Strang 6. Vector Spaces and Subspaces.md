---
date updated: 2022-04-22 18:27

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

## Vector Spaces and Subspaces
[[18.06  Linear Algebra Strang]]
#### Definition; $\R^n$ and other vector spaces

A <font color=gree>vector space</font> is a set of vectors that is closed under addition and scalar multiplication: given space $S$: $A,B \in S$ implies $cA + dB \in S$. $\mathbb{R}^n$ are all vector spaces. In other words: all linear combinations of vectors in a space are also in the space. Note that this necessitates that the origin is in every vector space. 

Other vector spaces: $\mathbf{M}^2$, the set of all $2 \times 2$ matrices. $\mathbf{F}$, the set of all real functions. $Z$, the zero vector.

#### Properties of Vector Spaces

Formally, in vector space, the operations of vector addition and scalar multiplication have these properties:
- $x + y = y + x$
- $x + (y + z) = (x + y) + z$
- There is a unique $0$ vector such that $x + 0 = x$
- For each $x$ there exists unique $-x$ such that $x + -x = 0$
- $1 \times x = x$
- $(c_1c_2)x = c_1(c_2 x)$
- $c(x + y) = cx + cy$
- $(c_1 + c_2)x = c_1 x + c_2 x$

When we're talking about spaces like $\R^n$ we get a lot of this stuff for free.

#### Subspaces

A <font color=gree>subspace</font> is a vector space wholly contained in another. Consider a line through the origin; for simplicity, the $x$-axis in $\mathbb{R}^2$. All these vectors can be written $(a,0)$. Then we can see that $c(a,0) + d(b,0) = (ca + db,0)$. So this is a vector space - call it $S$. Since every vector $(a,0)$ is in $\mathbb{R}^2$,  we can say that $S \subset \R^2$. 

The subspaces of $\R^2$ are: 
- $\R^2$ itself;
- All lines through the origin;
- and the origin itself ( which every subspace contains)

Note that if $P$ and $L$ are subspaces, then $P \cup L$ is not necessarily a subspace, but $P \cap L$ is. Proof: If $v,w$ are in $P$, then they are in $L$. Then (since $P$ and $L$ are subspaces) it follows that $av + bw$ are in $P$, and that $av + bw$ are in $L$, meaning $av + bw$ are in $P \cap L$.


## Column Spaces

Now we are moving on to vector spaces associated with a particular matrix. 

The <font color=gree>Column Space</font> of a matrix is the space that is made up of all linear combinations of its columns. So, imagine:

$$A = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 1 & 3 \\ 3& 1 & 4\\ 4& 1 & 5\end{bmatrix}$$
Each column is a vector in $\R^4$. So the column space of $A$ is a subspace of $\R^4$. We can call it $C(A)$. 

Does $Ax = b$ have unique solutions for all $b$? 

$$Ax = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 1 & 3 \\ 3&1 & 4\\ 4 & 1 & 5 \end{bmatrix}\begin{bmatrix} x_1 \\ x_2 \\x_3 \end{bmatrix} = \begin{bmatrix} b_1 \\ b_2 \\ b_3 \\b_4\end{bmatrix}$$
We can conceptualize this as linear combinations of columns of $A$: 
$$Ax = x_1\begin{bmatrix} 1\\2\\3\\4\end{bmatrix} + x_2 \begin{bmatrix} 1 \\1 \\1 \\1\end{bmatrix} + x_3 \begin{bmatrix} 2\\3\\4\\5\end{bmatrix}= \begin{bmatrix} b_1 \\ b_2 \\ b_3 \\b_4\end{bmatrix}$$

We want $b$ that are linear combinations of the columns of $A$ - the column space of $A$. There are many $b$ we can't get - this is like saying that $C(A) \subset \R^4$. 

The columns of $A$ are linearly dependent, causing problems. We will later discover that columns 1 and 2 are the <font color=gree>pivot columns</font> of $A$, meaning that throwing out column $3$ does nothing to the column space (we could say the same for column $1$ - by convention, we go left to right).

```ad-important
title:
$Ax = b$ is solvable if and only if $b \in C(A)$. 
```

We can generalize this a bit. For any set of vectors $S$ in vector space $V$, the space $SS$ - all linear combinations of elements of $S$ - is the subspace of $V$ <font color=gree>spanned</font> by $S$. $SS$ is the <font color=gree>span</font> of $S$. 

For instance, $(1,0,0), (0,1,0)$ and $(0,0,1)$ span $\R^3$. 


## Null Space

Let's have the same $A$ as before. 

 
$$Ax = x_1\begin{bmatrix} 1\\2\\3\\4\end{bmatrix} + x_2 \begin{bmatrix} 1 \\1 \\1 \\1\end{bmatrix} + x_3 \begin{bmatrix} 2\\3\\4\\5\end{bmatrix}= \begin{bmatrix} b_1 \\ b_2 \\ b_3 \\b_4\end{bmatrix}$$
We can solve this for e.g. $b = 0$ easily. Too easily, it turns out. $x_1 = x_2 = 1, x_3 = -1$ works. But so does $x_1 = x_2 =2, x_3 = -2$. Matrix $A$ sends that whole plane $x_1 + x_2 - x_3 = 0$ to $0$ (Incidentally, meaning $A$ is singular). 

This means the <font color=gree>null space</font> of $A$ is the plane above.  