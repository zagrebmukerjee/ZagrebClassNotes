---
date updated: 2021-06-10 19:20

notetype: "Math Class Note"
cssclass: math-class-note

tags:
  - '#classNotes'
---

#### [[Video 4 Matrix Multiplication as Composition]]
Part of [[@Review of Linear Algebra Index]]
- [[#How to apply two successive transformations?|How to apply two successive transformations?]]
- [[#Computing Transformation Composition: Example|Computing Transformation Composition: Example]]
- [[#General Transformation Composition: Advanced|General Transformation Composition: Advanced]]

Builds directly on [[Video 3 Linear Transformations and Matrices|Video 3]] 

##### How to apply two successive transformations?

Let $L$ and $M$ be linear transformations. There exists some $N$ such that $N(\mathbf{v}) = L(M(\mathbf{v}))$. But how to find it?

Return to the core concept of basis from [[Video 2 Linear Combinations, Span, and Basis Vectors|Video 2]]. Where do $\mathbf{\hat{i}}$ and $\mathbf{\hat{j}}$ go?

Suppose $L$ is a shear, and $M$ is a 90$^\circ$ rotation. 

$$ M = \begin{bmatrix} 0 & -1 \\ 1 & 0\end{bmatrix} \qquad L = \begin{bmatrix} 1 & 1 \\ 0 & 1\end{bmatrix}$$
We can look at it geometrically, and see the composition:

![[Pasted image 20210610192919.png]]

Looks like $\mathbf{\hat{i}}$ goes to $\begin{bmatrix}1\\1\end{bmatrix}$ and $\mathbf{\hat{j}}$ goes to $\begin{bmatrix}-1\\0\end{bmatrix}$, so $N$ is $\begin{bmatrix}1 & -1\\1 & 0\end{bmatrix}$. How do we get here mathematically?

##### Computing Transformation Composition: Example
Let $L$ and $M$ be defined as below
$$ M = \begin{bmatrix} 1 & -2 \\ 1 & 0\end{bmatrix} \qquad L = \begin{bmatrix} 0 & 2 \\ 1 & 0\end{bmatrix}$$

$$L(M(\mathbf{v})) = \ \begin{bmatrix} 0 & 2 \\ 1 & 0\end{bmatrix}\left(\begin{bmatrix} 1 \\ 1 \end{bmatrix}v_1\right) \&   \begin{bmatrix} 0 & 2 \\ 1 & 0\end{bmatrix}\left(\begin{bmatrix} -2 \\ 0 \end{bmatrix}v_2\right) $$

$$ N = \ \begin{bmatrix} 0 & 2 \\ 1 & 0\end{bmatrix}\begin{bmatrix} 1 \\ 1 \end{bmatrix} \&    \begin{bmatrix} 0 & 2 \\ 1 & 0\end{bmatrix}\begin{bmatrix} -2 \\ 0 \end{bmatrix}$$

$$N = \begin{bmatrix} 0 \\ 1 \end{bmatrix}1 + \begin{bmatrix} 2 \\ 0 \end{bmatrix}1  \quad \& \quad  \begin{bmatrix} 0 \\ 1 \end{bmatrix}(-2) + \begin{bmatrix} 2 \\ 0 \end{bmatrix}0 $$

$$ N = \begin{bmatrix} 2 \\ 1 \end{bmatrix} \& \begin{bmatrix} 0 \\ -2 \end{bmatrix} = \begin{bmatrix} 2 & 0 \\ 1 & -2 \end{bmatrix} $$

The geometric notion makes it very easy to see, for example, that matrix multiplication is associative:

$$A(BC) = (AB)C$$

Note, however, that it is NOT transitive:

$$AB \neq BA$$

##### General Transformation Composition: Advanced

See [[Video 9 Dot Product and Duality|Video 9]] for information on the dot product.

This method generalizes to any 2D matrices, or 3D. The row-column trick is based on this: let $A$ be $m*k$ and $B$ be $k*n$. Then $C= AB$ can be constructed with $c_{i,j}$ being the dot product of the $i$<sup>th</sup> row of $A$ and the $j$<sup>th</sup> column of $B$. 

$$c_{1,1} = (a_{1,1} \ldots a_{1,k}) \: \cdot \: (b_{1,1} \ldots b_{k,1}) $$

Note that, since these vectors have the same length, the dot product is defined, and so
$$c_{1,1} = a_{1,1} b_{1,1} + a_{1,2}b_{2,1} + \ldots a_{1,k} b_{k,1}$$

$$c_{3,5} = a_{3,1} b_{1,5} + a_{3,2}b_{2,5} + \ldots a_{3,k} b_{k,5}$$

