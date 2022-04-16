---
date updated: 2022-03-21 16:53

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes/math/linalg'
- '#🚧'
---

# [[Strang 3. Multiplication and Inverses]]

For my next trick I will try to unlearn the effective but conceptually limiting method of matrix multiplication that I've used for ~ 15 years...

Let $A$ be a matrix: then $A_{i,*}$ is the $i^{th}$ row of $A$, and $A_{*,j}$ the $j^{th}$ column.

Suppose matrices $A$ and $B$. $AB$ is defined if $A$ is $m \times n$ and $B$ is $n \times k$; we can say that $A$ and $B$ are 'conformable'. If they are, then let $AB = C$;

$$C_{i,j} = A_{i,*} \cdot B_{*,j}$$
in other words, entry $C_{ij}$ is the dot product of row $i$ of $A$ and column $j$ of $B$. 

Another way to get $C$:

$$C = \begin{bmatrix}AB_{*,1}, AB_{*,2}, \ldots AB_{*,k}\end{bmatrix}$$