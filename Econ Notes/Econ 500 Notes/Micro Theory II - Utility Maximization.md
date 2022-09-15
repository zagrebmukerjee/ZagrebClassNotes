---
aliases:
creation date: Monday, September 12th 2022, 11:53 am
date updated: Thursday, September 15th 2022, 9:04 am

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

#### Implication 1
Homogeneity of degree zero can be differentiated wrt $\lambda$: 
$$\begin{align}
0 &= x(\lambda p, \lambda w) - x(p,w) \\
&= x_\l(\lambda p, \lambda w) - x_\l(p, w)\\
\frac{\partial}{\partial \lambda} 0 &= \frac{\partial}{\partial \lambda} x_\l(\lambda p, \lambda w) - \frac{\partial}{\partial \lambda} x_\l(p, w) \\ 
0 &= p\frac{\partial x_\l(p,w)}{\partial p} + w \frac{\partial x_\l(p,w)}{\partial w} \\
&= \sum_k p_k\frac{\partial x_\l(p,w)}{\partial p_k} + w\frac{\partial x_\l(p,w)}{\partial w} 
\end{align}$$
<font color=#F7B801>Lec slides say 'evaluate at λ = 1'. why do I have to do that? I don't want to</font>

Suppose I want to express this in terms of the elasticities of good $\l$. I can do that by dividing thru by $x_\l(p,w)$ to get:

$$ \sum_k \epsilon_{\l k} + \epsilon_{\l w} = 0$$
Intuitively, this means that if I were to change all the prices a tiny percentage amount and also change the income the same tiny percentage amount, the demand for good $\l$ wouldn't change. 


#### Implication 2

Walras' law can be differentiated by some $p_k$: 

$$\begin{align}
w &= px(p,w) \\
\frac{\partial w}{\partial p_k} &= \frac{\partial px(p,w)}{\partial p_k} \\
0 &= p\frac{\partial x(p,w)}{\partial p_k} + x(p,w) \frac{\partial p}{\partial p_k}\\
0 &= \sum_\l p_\l \frac{\partial x_\l(p,w)}{\partial p_k} + x_k(p,w) 
\end{align}$$
recalling that $p,x$ are vectors. 

This can be turned into an elasticity with annoying stuff

$$\begin{align}
0 &= \sum_\l p_\l \frac{\partial x_\l(p,w)}{\partial p_k} + x_k(p,w) \\
&= \frac{p_k}{w} \sum_\l p_\l \frac{x_\l(p,w)}{x_\l(p,w) } \frac{\partial x_\l(p,w)}{\partial p_k} + \frac{p_k}{w} x_k(p,w)\\
&= \sum_\l \frac{p_\l x_\l(p,w)}{w}\left[\frac{\partial x_\l(p,w)}{\partial p_k} \frac{p_k}{x_\l(p,w)}\right] + \frac{p_k x_k(p,w)}{w} \\
&= \sum_\l \frac{p_\l x_\l(p,w)}{w}\epsilon_{\l k} + \frac{p_k x_k(p,w)}{w} \\
&= \sum_\l b_\l \epsilon_{\l k} + b_k
\end{align}$$
where $b_i$ is the budget share of good $i$. 

