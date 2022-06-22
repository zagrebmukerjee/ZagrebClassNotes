---
aliases:
creation date: 2022-06-20 19:01
date updated: 2022-06-20 19:01

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/linalg'
---

# [[Strang 14. Orthogonality]]


"The Big Picture of 18.06"
![[Pasted image 20220620190138.png]]

Orthogonal means the same as perpendicular. 

## Orthogonal Vectors

### Definition of Orthogonality
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

*Example*: triangle outlined by vectors $(0, 3)$, $(4,0)$, $(3,4)$. This is the classic 3-4-5 triangle, where $3^2 + 4^2 = 9 + 16 = 25$. It's immediately clear that the dot product of the sides is zero (this holds for any $x$ and $y$ axis vectors).

But now let's rotate this $45^\circ$ degrees, with the matrix 
$$ R = \begin{bmatrix} 
\cos 45^\circ & -\sin 45^\circ \\
\sin 45^\circ & \cos 45^\circ
\end{bmatrix} = \begin{bmatrix} - 1/4 &  \\ & -1/4 \end{bmatrix}$$


```