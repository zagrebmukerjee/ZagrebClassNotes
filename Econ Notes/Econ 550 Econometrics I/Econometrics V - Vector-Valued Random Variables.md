---
aliases:
creation date: 2022-10-04 12:47
date updated: 2022-10-04 12:47

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Econometrics V - Vector-Valued Random Variables]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


A random vector is a vector of random variables. The fundamentals are the same: for any $B \in \mathcal B$,
$$P(X \in B) = P_X(B) = P\{\omega \in \Omega: X(\omega) \in B \}$$
Now though we make this claim for $\mathcal B$ in $\R^n$. 

The (cumulative) distribution function is defined element-wise: $F_X(x) = P(X \leq x) = P(X_1 \leq x_1 \cap X_2 \leq x_2 \cap \ldots)$
Again, knowing $F$ gives us $P_X$.

```ad-example
title: Example in $\R^2$

Suppose $a < b$, $c< d$, and we have $X = X_1, X_2$. Then let $A = (a,b] \times (c, d]$; a square in $\R^2$. Then we can say: 
$$\begin{align}
P(X \in A) &= P(X_1 \in (a, b] \cap X_2 \in (c,d])\\
&= P(X_1 \leq b \cap X_1 > a \cap X_2 \leq d \cap X_2 > c)\\
&= P(X_1 \leq b \cap (X_1 \leq a)^c \cap X_2 \leq c \cap (X_2 \leq d)^c)\\
&= F_{12}(a,c) + F_{12}(b,d)
\end{align}$$
```

The density function $f_X(x)$ is $\frac{\partial^n F_X}{\partial x_1 \ldots \partial x_n}$ where $F_X$ is differentiable (which we've said is almost everywhere). This is compatible with the RN-theorem derivative construction based on the measure $P_X$. We can then say that 

$$P_X(X\in A) = \int_A f_X(x_1, \ldots ) dx_1 \ldots dx_n$$
which is an $n-$integral. 

