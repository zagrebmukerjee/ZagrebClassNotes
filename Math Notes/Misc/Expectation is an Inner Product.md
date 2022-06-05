---
aliases:
creation date: 2022-06-05 13:31
date updated: Sunday, June 5th 2022, 1:45 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math'
- '#types/classes/math/linalg'
- '#types/classes/stat'
- '#status/🚧'
---

# [[Expectation is an Inner Product]]

Over the set of random variables, define an inner product:
$$ \langle X, Y \rangle  = E(XY)$$
The latter is the expected value of the product of $XY$. Given a joint pdf $f(x,y)$ this is defined as 
$$E(XY) = \iint xyf(x,y) \, dy dx$$

We have the desired properties:
- Positive semidefinite: $\langle X,X \rangle = E(X^2) \geq 0$
- Symmetry: $\langle X,Y \rangle = E(XY) = E(YX) = \langle X,Y \rangle$
- Linearity: 

$$\begin{align}
\langle aX_1 + bX_2, Y\rangle  &= E[(aX_1 + bX_2)Y]\\
&= \iiint (ax_1 + bx_2)y\; dx_1 dx_2 dy \\
&= \iiint[ ayx_1 + by x_2] \; dx_1 dx_2 dy \\
&= a\iint yx_1 \; dx_1 dy + b\iint yx_2 \; dx_2 dy\\
&= aE(X_1Y) + bE(X_2Y) \\
&= a\langle X_1,Y\rangle + b\langle X_2, Y\rangle \\
\end{align}$$
