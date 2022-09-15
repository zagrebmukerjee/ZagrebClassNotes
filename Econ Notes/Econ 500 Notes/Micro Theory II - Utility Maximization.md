---
aliases:
creation date: Monday, September 12th 2022, 11:53 am
date updated: Thursday, September 15th 2022, 8:47 am

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



### Implications

Homogeneity of degree zero says: 
$$\begin{align}
0 &= x(\lambda p, \lambda w) - x(p,w) \\
&= x_\l(\lambda p, \lambda w) - x_\l(p, w)\\
\frac{\partial}{\partial \lambda} 0 &= \frac{\partial}{\partial \lambda} x_\l(\lambda p, \lambda w) - \frac{\partial}{\partial \lambda} x_\l(p, w) \\ 
0 &= p\frac{\partial x_\l(p,w)}{\partial p} + w \frac{\partial x_\l(p,w)}{\partial w} \\
&= \sum_k p_k\frac{\partial x_\l(p,w)}{\partial p_k} + w\frac{\partial x_\l(p,w)}{\partial w} 
\end{align}$$
<font color=#F7B801>Lec slides say 'evaluate at λ = 1'. why do I have to do that? I don't want to</font>

Suppose I want to express this in terms of the elasticities of good $\l$. I can do that by dividing thru by $x_\l(p,w)$ to get:

$$ \sum_k \epsilon_{\l k} + w \epsilon_{\l w} = 0$$

