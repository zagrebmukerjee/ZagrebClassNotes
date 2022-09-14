---
aliases:
creation date: Monday, September 12th 2022, 11:53 am
date updated: Wednesday, September 14th 2022, 2:23 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#topics/econ/theory/micro'
---

# [[Micro Theory II - Utility Maximization]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


Why not just start here? Well, it's good to have the foundations. And in various analytic contexts one might prefer to use choice functions or preferences. 


## Introduction

We have a constrained optimization problem: 
- Maximize $U: X \to \R$
- subject to $px \leq w$

Can I solve this? Yes - thanks to the Weierstrass Extreme Value Theorem, which tells us that a continuous function from a compact set to a subset of $\R$ has a minimum/maximum. It's nice for us that the budget set is compact. Generally we assume continuity of $U$, also strict increasingness. We don't need to have strict increasingness of utility/strict monotonicity of preferences. We like to have $px = w$ so we can do optimization. 

Write $x(p,w)$ is the maximizer of utility given $p,w$. We can write two conditions on $x$: 
- Homogeneous of degree zero. $x(\lambda p, \lambda w) = \lambda^0 x(p,w)$. (later we will have homogeneity of degree >0). 
- Walras' law: Every $px_i >0$ means that $px = w$ for all $x \in x(p,w)$. In other words, you spend all your money. We get this easily from monotonicity. 

```ad-important
title: Elasticities 



```

In utility maximization and other calculus problems we'll have quantities like $\frac{\partial x_i(p,w)}{\partial p_k}$. This tells you: if the price of good $k$ increases a tiny amount, how much more good $x_i$ will you demand? For normalization reasons, we might want this in percentage terms: If the price of good $k$ increases by $q \%$, by what percentage will demand for $x_i$ increase? 

We can get this by turning our 'tiny amounts' into 'tiny percentages':
$$\epsilon_{ik} = \frac{\partial x_i(p,w)}{x_i(p,w)} \big/ \frac{\partial p_k}{p_k} = \frac{\partial x_i(p,w)}{\partial p_k} \cdot \frac{p_k}{x_i(p.w)}$$Observing that $\frac{\partial}{\partial x} \log a(x) = a(x)/a$, we can then turn this into 


### Implications
Homogeneity of degree zero says: 
$$\begin{align}
0 &= x(\lambda p, \lambda w) - x(p,w) \\
&= x_\l(\lambda p, \lambda w) - x_\l(p, w)\\
\frac{\partial}{\partial \lambda} 0 &= \frac{\partial}{\partial \lambda} x_\l(\lambda p, \lambda w) - \frac{\partial}{\partial \lambda} x_\l(p, w) \\ 
0 &= \lambda \frac{\partial x_\l(p,w)}{\partial p} + \lambda \frac{\partial x_\l(p,w)}{\partial w} \\
&= \sum_k \frac{\partial x_\l(p,w)}{\partial p_k} + \frac{\partial x_\l(p,w)}{\partial w} 
\end{align}$$
