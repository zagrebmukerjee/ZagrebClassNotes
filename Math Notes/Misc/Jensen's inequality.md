---
aliases: 
date updated: Friday, October 7th 2022, 12:30 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
creation date: Wednesday, April 27th 2022, 3:20 pm
---

### Jensen's Inequality

#### Concave Functions
Suppose $f$ is concave - that is to say $f''<0$. Then:
$$tf(a) + (1-t)f(b) < f(ta + (1-t) b)$$ Other statements:
The secant of a convex (concave) function lies above (below) the functions

![[Pasted image 20220427152619.png|250]]

#### Expectations

If X is a random variable with finite first moment, and $g$ is a convex function, then 
$$E[g(X)] > g(E[X]) $$
```ad-example
title:
Consider the squared mean of a dice-roll - $(4 + 3)^2/2^2$,  $49/4$, or $12.25$, versus the mean of the squares, $\frac{1}{6}[36 + 25 + 16 + 9 + 4+ 1]$ = $91/6 = 15.166$
```
#### Proof
Suppose $g()$ convex. Then there is a hyperplane below $g(x)$ and tangent to $g(x)$ at $EX$ - call it $h(x)$.

Then:
$$\begin{align}
g(EX) &= h(EX)\\
&= Eh(X)\\
&\leq Eg(X)
\end{align}$$
recalling that expectation is linear and monotonic. 
