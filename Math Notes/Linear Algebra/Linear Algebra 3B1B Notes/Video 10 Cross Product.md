---
date updated: 2021-06-14 22:48

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

#### [[Video 10 Cross Product]]

##### Length of the cross product

Think of $\mathbf{v}$ and $\mathbf{w}$ as forming a paralellogram. Let $C(\mathbf{v}, \mathbf{w})$ be the area of that paralellogram, which is positive if $\mathbf{v}$ is to the right of $\mathbf{w}$, and negative if vice versa. 

This means it's not commutative - $C(\mathbf{v},\mathbf{w}) = -C(\mathbf{w}, \mathbf{v})$. But $sC(\mathbf{v},\mathbf{w}) = C(s\mathbf{v},s\mathbf{w})$.

$$C(\mathbf{\hat{i}},\mathbf{\hat{j}})  = 1$$

$$C(\mathbf{\hat{j}},\mathbf{\hat{i}})  = -1$$

Computing $C$ is simple: the determinant of the matrix with columns  $\mathbf{v}$ and $\mathbf{w}$ . 

Thus, _ceteris paribus_ the more perpendicular  $\mathbf{v}$ and $\mathbf{w}$, the greater their cross product. 

##### The Cross Product

The cross product maps 2 3D vectors to another 3D vector that is perpendicular to the others, with length determined by $C$ above and sign according to the right-hand rule. 