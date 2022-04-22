---
date updated: 2022-04-20 20:05

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
- '#status/🚧'
---


First, a few foundational concepts. 


## Permutation

We can represent row switches as permutation matrices: Exchanging row $2$ and row 1 of a $3 \times 3$ matrix is

$$ \begin{bmatrix} 0 & 1 & 0 \\ 1 &0 & 0 \\ 0 & 0 & 1 \end{bmatrix}$$
 If row changes are required, we can change $A = LU$ into $PA = LU$ where $P$ does the row exchanges and $L$ does the elimination. 

$P$ is always an identity matrix, with reordered rows (or not). There are $n!$ permutation matrices of size $n \times n$. For all $P$, $P'P = I$, and/or $P' = P^{-1}$. 

## Transposes
Transposition is exchanging the rows and columns of a matrix. We write the transpose of $A$ as $A'$ or $A^T$. $A'_{ij} = A_{ji}$. 

$A$ is <font color=gree>symmetric</font> iff $A' = A$. $(AB)' = B'A'$.

If $R$ is rectangular, then $R'R$ is symmetric. Proof: Let $Q = R'R$. Then what is $Q_{ij}$? It is the dot product of the $i^{th}$ row of $R'$ and the $j\th$ column of $R$. But the columns of $R$ are the rows of $R'$. So this is the same as the dot product of the $j\th$ row of $R'$ and the $i\th$ column of $R$ - or $Q_{ji}$. So $Q_{ij} = Q_{ji}$ and thus $R'R$ is symmetric. 

A simpler way: $(R'R)' = R'R$.

## Vector Spaces and Subspaces

A <font color=gree>vector space</font> is a set of vectors that is closed under addition and scalar multiplication: given space $S$: $A,B \in S$ implies $cA + dB \in S$. $\mathbb{R}^n$ are all vector spaces. In other words: all linear combinations of vectors in a space are also in the space. Note that this necessitates that the origin is in every vector space. 

A <font color=gree>subspace</font> is a vector space wholly contained in another. Consider a line through the origin; for simplicity, the $x$-axis in $\mathbb{R}^2$. All these vectors can be written $(a,0)$. Then we can see that $c(a,0) + d(b,0) = (ca + db,0)$. So this is a vector space - call it $S$. Since every vector $(a,0)$ is in $\mathbb{R}^2$,  we can say that $S \subset \R^2$. 

The subspaces of $\R^2$ are: 
- $\R^2$ itself;
- All lines through the origin;
- and the origin itself. 
