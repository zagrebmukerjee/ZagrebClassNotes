---
aliases:
creation date: Sunday, March 5th 2023, 2:36 pm
date updated: Sunday, March 5th 2023, 2:46 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Law of Iterated Expectation]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


For continuous RVs $X, Y$, with $E|Y| < \infty$:

$$ E[Y] = E_X[E[Y|X]] $$
Proof: 

$$\begin{align}
E_X [E[Y|X]] &= \int E[Y|X=x]f_X(x) dx \\
&= \int_{\Omega_X} \left[ \int_{\Omega_Y} y f_{Y|X}(x,y) dy \right]f_X(x) dx \\
&= \int_{\Omega_X} \left[ \int_{\Omega_Y} y \frac{f_{XY}(x,y)}{f_X(x)} dy \right]f_X(x) dx\\
&= \int_{\Omega_X} \int_{\Omega_Y} y f_{XY}(x,y) dy dx\\
&= \int_{\Omega_Y} \int_{\Omega_X} y f_{XY}(x,y) dx dy\\
&= \int_{\Omega_Y}y f_Y(y) dy \\
&= E[Y]
\end{align}$$

In order, the steps used: definition of expectation, definition of conditional expectation, definition of conditional density, algebra, Fubini's theorem, definition of marginal density, and definition of expectation.

It helps to remember the intuition that $E[Y|X]$ is some function $g(X)$; so $E[Y]$ is the same as evaluating that function over all (weighted) values of $X$. 


This can also be nested: 

$$ E[X|Y] = E_Z[E[X|Y,Z]]$$
$$ E[Y] = E_{X,Z}[E[Y|X,Z]]$$


```ad-example
title:

Say I want to know earnings from the census of a population. If $f_Y$ is the density of earnings, I can simply take

$$E[Y] = \int Y f(Y) dy$$

But I can also measure the earnings conditional on sex: 
$$ E[Y] = P(\text{Male})\int Y f(Y) \mathbb 1[\text{Male}]dy + P(\text{Female})\int Y f(Y) \mathbb 1[\text{Female}]dy$$
$$ E[Y] = E[E[Y|\text{Sex}]]$$

If I want to know the earnings of, say, the male subpopulation, I can also subdivide that: 
$$\begin{align}
E[Y|\text{Sex} = \text{Male}] &= \int Y f(Y) \mathbb 1[\text{Male}]dy\\
&= \text{Male}] = \int Y f(Y) \mathbb 1[\text{Male}]\mathbb 1[\text{College}]dy + \int Y f(Y) \mathbb 1[\text{Male}]\mathbb 1[\text{No College}]dy\\
&= E[E[Y|\text{Sex} = \text{Male}, \text{College}]]\\
\end{align}$$

And finally, I can use a double-breakdown to get the unconditional expectation of $Y$ again: 

$$\begin{align}
E[Y] &= \sum_\text{s}\sum_{c} P(\text{College} = c)P(\text{Sex} = s) \int Y f(Y)\mathbb 1[\text{s}]\mathbb 1[\text{c}] dy\\
&= E[E[Y|\text{Sex}, \text{College}]]
\end{align}$$

```
