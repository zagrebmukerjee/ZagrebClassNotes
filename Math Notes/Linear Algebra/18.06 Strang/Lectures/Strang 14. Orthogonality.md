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
[[18.06 Linear Algebra Strang]]

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

### "Fundamental Theorem of Linear Algebra" Part 1

So the null space and the row space 'carve up' $\R^n$: Since every vector in $C(A')$ is orthogonal to every vector in $N(A)$, and their dimensions together make $n$, their two bases make an $n$ element basis for $\R^n$.

Another way of putting it: The nullspace and rowspace are orthogonal complements in $\R^n$. The null space consists of *every* vector that is orthogonal to every vector in the row space, and vice versa. 

## Preview

We want to reason about $Ax = b$ when there is no solution. For instance, $A$ might be my observations of something - e.g. a blood pressure, so $m$ is whatever number of observations, $n$ is $2$ (s/d pressure), or the position of a satellite. 

Then there's a system of equations where each row is parameters, $b$ is your findings. Almost always no solution. There's only one blood pressure. Can't solve $Ax = b$. Could throw away all but $1$ observation but that's pretty wasteful. What to do?

A related matrix, that will play a key role in Ch4.

### Quadratic Form
Let's jump ahead to a crucial matrix, key to Ch4: $A'A$. It's square, and symmetric,  sometimes invertible. 

When we can't solve $Ax = b$, look at $A'A \hat x = A'b$, hoping we can find that solution $\hat x$ and say that's the best solution for $Ax = b$. 

When is $A'A$ invertible? Example: 

$$A = \begin{bmatrix} 1 & 1 \\ 1 & 2 \\ 1 & 5\end{bmatrix} \qquad A'A = \begin{bmatrix} 1 & 1 & 1 \\ 1 & 2 & 5  \end{bmatrix}\begin{bmatrix} 1 & 1 \\ 1 & 2 \\ 1 & 5\end{bmatrix} = \begin{bmatrix} 3 & 8 \\5 & 30\end{bmatrix}$$

This is evidently full rank/invertible. But eg. if $A$ is rank $1$, then $A'A$, the product of two rank-$1$ matrices, can't have rank $>1$. 

```ad-important
title:
$A'A$ is invertible only if $A$ has full column rank.

```

Key point!

$N(A'A) = N(A)$, and $\text{rank}(A'A) = \text{rank}(A)$. 

