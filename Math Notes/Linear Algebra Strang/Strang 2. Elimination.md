---
date updated: 2022-03-21 13:23

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes/math/linalg'
- '#🚧'
---

# [[Strang 2. Elimination]]
Part of [[@Review of Linear Algebra Index]]


- How to solve systems of equations? Turn it into an augmented matrix and eliminate. 
- Want to do elementary row operations until you have an upper-triangular matrix. Then can 'back-substitute'
- The diagonal elements of the reduced matrix are 'pivots'. Determinants are product of pivots
- The pivots can't be zero. If they are forced to be, and you can't fix it through exchanging or adding rows, then system is unsolvable $\iff$ matrix is singular

- Suppose $A$ is a matrix and $U$ is the upper-triangular matrix resulting from elimination. Let $E_1$ be the matrix that represents the first step of elimination - i.e., if elimination has $n$ steps, $E_n E_{n-1} \ldots E_2 E_1 A = u$. 
- $E$ is the product of those elimination matrices. 
