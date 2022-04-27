---
date updated: 2022-04-20 20:05

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---


First, a few foundational concepts. 
[[18.06 Strang]]

## Permutation

We can represent row switches as permutation matrices: Exchanging row $2$ and row 1 of a $3 \times 3$ matrix is

$$ \begin{bmatrix} 0 & 1 & 0 \\ 1 &0 & 0 \\ 0 & 0 & 1 \end{bmatrix}$$
 If row changes are required, we can change $A = LU$ into $PA = LU$ where $P$ does the row exchanges and $L$ does the elimination. 

$P$ is always an identity matrix, with reordered rows (or not). There are $n!$ permutation matrices of size $n \times n$. For all $P$, $P'P = I$, and/or $P' = P^{-1}$. 

## Transposes
Transposition is exchanging the rows and columns of a matrix. We write the transpose of $A$ as $A'$ or $A^T$. $A'_{ij} = A_{ji}$. 

#### Properties of Transpose
- $(A + B)' = A' + B'$
- $(AB)' = B'A'$
- $(A\inv)' = (A')\inv$
 

#### Symmetric Matrices
- $A$ is <font color=gree>symmetric</font> iff $A' = A$. $(AB)' = B'A'$.
If $R$ is rectangular, then $R'R$ is symmetric. Proof: Let $Q = R'R$. Then what is $Q_{ij}$? It is the dot product of the $i^{th}$ row of $R'$ and the $j\th$ column of $R$. But the columns of $R$ are the rows of $R'$. So this is the same as the dot product of the $j\th$ row of $R'$ and the $i\th$ column of $R$ - or $Q_{ji}$. So $Q_{ij} = Q_{ji}$ and thus $R'R$ is symmetric. 

A simpler way: $(R'R)' = R'R$.


## Vector Spaces intro
Moved to [[Strang 6. Vector Spaces and Subspaces]] for consonance