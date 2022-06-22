---
aliases:
creation date: 2022-06-20 19:01
date updated: Wednesday, June 22nd 2022, 11:57 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 14. Orthogonality]]


"The Big Picture of 18.06"
![[Pasted image 20220620190138.png]]

Orthogonal means the same as perpendicular. 

## Definition of Orthogonal Vectors

Two vectors are orthogonal exactly if their inner product (dot product) is zero.

```ad-note
title: Geometric Orthogonality

Recall the Pythagorean Theorem: A triangle is a right triangle iff sides follow $a^2 + b^2 = c^2$. 
In other words, if the sides are vectors, 
$$ ||x||^2 + ||y||^2 = ||x + y||^2$$
So when is this true? Recalling the definition of length, we can write this as:

$$\begin{align}
\sum x_i^2 + \sum y_i^2 &= \sum (x_i + y_i)^2 \\
&= \sum [x_i^2 + 2x_iy_i + y_i^2] \\
&= \sum x_i^2 + \sum y_i^2 + 2\sum x_i y_i \\
0 &= \sum x_i y_i \\
\end{align}$$

In other words, the condition of the Pythagorean theorem is the same as the dot-product-zero condition. 

**Example**: Consider the triangle outlined by vectors $a = (0, 3)$, $b = (4,0)$; then the hypotenuse is a line drawn from $y=3$ to $x = 4$, a reflection and translation of $c = (3,4)$. This is the classic 3-4-5 triangle, where $3^2 + 4^2 = 9 + 16 = 25$. It's immediately clear that the dot product of the sides is zero (this holds for any $x$ and $y$ axis vectors).

But now let's rotate this $45^\circ$ degrees, with the matrix 
$$ R = \begin{bmatrix} 
\cos 45^\circ & -\sin 45^\circ \\
\sin 45^\circ & \cos 45^\circ
\end{bmatrix} = \begin{bmatrix} \sqrt{2}/2 &  -\sqrt{2}/2 \\ \sqrt{2}/2 & \sqrt{2}/2 \end{bmatrix}$$

$$Ra = \begin{bmatrix}-3\sqrt{2}/2 \\ 3\sqrt{2}/2 \end{bmatrix} \qquad Rb = \begin{bmatrix}2 \sqrt{2} \\ 2 \sqrt{2} \end{bmatrix}$$

Now the hypotenuse is the vector drawn between these two end points, which has an $x$ length of $2 \sqrt{2} - (-3\sqrt{2}/2) = 7\sqrt{2}/2$ and a $y$ length of $2\sqrt{2} - 3\sqrt{2}/2 = \sqrt{2}/2$. 

$$\begin{align}
a \cdot b = (-3\sqrt{2}/2*2\sqrt{2}) + (3\sqrt{2}/2*2\sqrt{2})= 6 - 6 &= 0 \\
||a||^2 = (-3\sqrt{2}/2)^2 + (-3\sqrt{2}/2)^2 &= 9 \\
||b||^2 = (2\sqrt{2})^2 + (2\sqrt{2})^2 &= 16 \\
||c||^2 = (7\sqrt{2}/2)^2 + (\sqrt{2}/2)^2 = 50/2 &= 25 \\
\end{align}$$

How nice.
 

```

## Definition of Orthogonal Subspaces

Two subspaces $A$ and $B$ are orthogonal if $(a \in A) \land (b \in B) \to a \perp b$; in other words, every vector in them is orthogonal. So, for instance, the $x$-axis and $y$-axis are orthogonal in $\R^n$. The $xz$-plane and $xy$-plane are not (in fact, they share members!)


## Orthogonality and the Four Fundamental Subpaces
**Claim:** The row space is orthogonal to the null space. 

**Proof:** Consider $m \times n$ matrix $A$, and $x = (x_1, \ldots x_n)$ in the null space of $A$. Let $A_{i,*}$ denote the $i\th$ row of $A$. Then $Ax = \begin{bmatrix}A_{1,*}x  & \ldots & A_{m,*}x \end{bmatrix}' = 0$. But the entries of this vector are precisely the dot products of the rows of $A$ with $x$. This means $x$ is orthogonal to the rows of $A$; and since the row space is those vectors spanned by the rows of $A$, that means $x$ is orthogonal to everything in the row space.
