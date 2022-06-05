---
aliases:
creation date: 2022-06-05 13:31
date updated: Sunday, June 5th 2022, 1:37 pm

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
$$E(XY) = \iint xyf(x,y) dy dx$$

We have the desired properties:
- Positive semidefinite: $\langle X,X \rangle = E(X^2) \geq 0$
- Symmetry: $\langle X,Y \rangle = E(XY) = E(YX) = \langle X,Y \rangle$
- Linearity: $E(
