---
aliases:
- "Marshallian demand"
creation date: Monday, September 12th 2022, 11:53 am
date updated: Saturday, November 26th 2022, 3:49 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#topics/econ/theory/micro'
---

# [[Micro Theory II - Utility Maximization]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 500 Micro Theory Index]]


Why not just start here? Well, it's good to have the foundations. And in various analytic contexts one might prefer to use choice functions or preferences. 


## Basic Properties

We have a constrained optimization problem: 
- Maximize $U: X \to \R$
- subject to $px \leq w$

Can I solve this? Yes - thanks to the Weierstrass Extreme Value Theorem, which tells us that a continuous function from a compact set to a subset of $\R$ has a minimum/maximum. It's nice for us that the budget set is compact. Generally we assume continuity of $U$, also strict increasingness. We don't need to have strict increasingness of utility/strict monotonicity of preferences. We like to have $px = w$ so we can do optimization. 

### Demand Function

Write $x(p,w)$ is the maximizer of utility given $p,w$. This is the <font color=gree>Marshallian Demand</font> or <font color=gree>Walrasian Demand.</font>

We can establish two conditions on $x$: 
- Homogeneous of degree zero. $x(\lambda p, \lambda w) = \lambda^0 x(p,w)$. (later we will have homogeneity of degree >0). 
- Walras' law: Every $px_i >0$ means that $px = w$ for all $x \in x(p,w)$. In other words, you spend all your money. We get this easily from monotonicity. 



### Implications

#### Implication 1
Homogeneity of degree zero can be differentiated wrt $\lambda$: 
$$\begin{align}
0 &= x(\lambda p, \lambda w) - x(p,w) \\
&= x_\l(\lambda p, \lambda w) - x_\l(p, w)\\
\frac{\partial}{\partial \lambda} 0 &= \frac{\partial}{\partial \lambda} x_\l(\lambda p, \lambda w) - \frac{\partial}{\partial \lambda} x_\l(p, w) \\ 
0 &= p\frac{\partial x_\l(\lambda p,\lambda w)}{\partial p} + w \frac{\partial x_\l(\lambda p,\
\lambda w)}{\partial w} \\
0 &= p\frac{\partial x_( p,w)}{\partial p} + w \frac{\partial x_\l(p,w)}{\partial w} \text{ evaluating at } \lambda = 1\\
&= \sum_k p_k\frac{\partial x_\l(p,w)}{\partial p_k} + w\frac{\partial x_\l(p,w)}{\partial w} 
\end{align}$$

Suppose I want to express this in terms of the elasticities of good $\l$. I can do that by dividing thru by $x_\l(p,w)$ to get:

$$ \sum_k \epsilon_{\l k} + \epsilon_{\l w} = 0$$
Intuitively, this means that if all prices go up $t\%$, and income goes up $t\%$, then $x_\l$ does not change for marginal-sized $t$. The fact that I have to evaluate at $\lambda = 1$ makes this a local condition. 


#### Implication 2

Walras' law can be differentiated by some $p_k$: 

$$\begin{align}
w &= px(p,w) \\
\frac{\partial w}{\partial p_k} &= \frac{\partial px(p,w)}{\partial p_k} \\
0 &= p\frac{\partial x(p,w)}{\partial p_k} + x(p,w) \frac{\partial p}{\partial p_k}\\
0 &= \sum_\l p_\l \frac{\partial x_\l(p,w)}{\partial p_k} + x_k(p,w) 
\end{align}$$
recalling that $p,x$ are vectors. 
Rearranging slightly sneakily gets us that 
$$ \partial p_k x_k(p,w) = - \sum_\l p_\l \partial x_\l(p,w)$$
A tiny change in $p$ doesn't change relative allocations, so at the margin we reduce all other demands accordingly. 

This can be turned into an elasticity with annoying stuff

$$\begin{align}
0 &= \sum_\l p_\l \frac{\partial x_\l(p,w)}{\partial p_k} + x_k(p,w) \\
&= \frac{p_k}{w} \sum_\l p_\l \frac{x_\l(p,w)}{x_\l(p,w) } \frac{\partial x_\l(p,w)}{\partial p_k} + \frac{p_k}{w} x_k(p,w)\\
&= \sum_\l \frac{p_\l x_\l(p,w)}{w}\left[\frac{\partial x_\l(p,w)}{\partial p_k} \frac{p_k}{x_\l(p,w)}\right] + \frac{p_k x_k(p,w)}{w} \\
&= \sum_\l \frac{p_\l x_\l(p,w)}{w}\epsilon_{\l k} + \frac{p_k x_k(p,w)}{w} \\
&= \sum_\l b_\l \epsilon_{\l k} + b_k
\end{align}$$
where $b_i$ is the budget share of good $i$. 
So my budget share for good $k$ is equal to all the other budget shares plus their elasticity wrt price $k$; so a tiny $\%$ change in prices would reallocate to every other good proportional to their elasticity.



#### Implication 3

While we're at it we can differentiate Walras' law by $w$ to get 
$$\begin{align}
w &= px(p,w) \\
1 &= p\frac{\partial x(p,w)}{\partial w}\\
&= \sum_\l p_\l \frac{\partial x_\l(p,w)}{\partial w}\\
\end{align}$$
Predictably we can turn this into an elasticity:

$$\begin{align}
1 &= \sum_\l p_\l \frac{\partial x_\l(p,w)}{\partial w}\\
&= \sum_\l p_\l \frac{x_\l(p,w) w}{x\l(p,w) w}\frac{\partial x_\l(p,w)}{\partial w} \\
&= \sum_\l \frac{p_l x_l(p,w)}{w} \left[ \frac{\partial x_\l(p,w)}{\partial w} \cdot \frac{w}{x_\l(p,w)}\right]\\
&= \sum_\l b_\l \epsilon_{\l w}
\end{align}$$
in other words; the sum of budget shares times elasticities is $1$. If income increases a marginal amount, the budget shares change according to elasticities. 


### Proposition 5

If $u$ is [[Micro Theory IIIa - Concave, Convex, Quasi|quasiconcave]] then $x(p,w)$ is convex. If $u$ is SQCV then $x(p,w)$ is a singleton satisfying WARP. 

#### Proof

1) Suppose $u$ quasiconcave. Choose $x, x''$ in $x(p,w)$. We want to show that $x'' = \lambda x + (1-\lambda)x'$ is in $x(p,w)$. 
We can say $p x'' = \lambda p x'+ (1-\lambda) p x' = w$. So $x''$ is feasible under $w$. 
Quasiconcavity of $u$ tells us that $u(x'') \geq \lambda u(x) + \lambda u(x')$. But $u(x'')$ cannot be greater than $u(x')$ or $u(x)$, since it is feasible under $w$. So $u(x'') = u(x)=u(x')$, and $x'' \in x(p,w)$. 

2) Suppose $u$ strictly QCV. Choose $x, x''$ in $x(p,w)$. We want to show that $x'' = \lambda x + (1-\lambda)x'$ is in $x(p,w)$. 
We can say $p x'' = \lambda p x'+ (1-\lambda) p x' = w$. So $x''$ is feasible under $w$. 
Strict quasiconcavity of $u$ tells us that $u(x'') \gt \lambda u(x) + \lambda u(x')$. But $u(x'')$ cannot be greater than $u(x')$ or $u(x)$, since it is feasible under $w$. So this is a contradiction - if $x', x'' \in x(p,w)$, then $x' = x''$. 


### First-Order Conditions

The problem is $\max_x u(x)$ subject to $px \leq w$. 
For an interior solution - on the budget set - we can have FOC that are 
$$\begin{align}
\lambda p_i &= \frac{\partial u}{\partial x_i}\\
w &= \sum p_i x_i \\
\end{align}$$
where $\lambda$ is a Lagrange multiplier. 

In this case we conventionally get rid of $\lambda$ by dividing it away. But we could also not do that, and interpret $\lambda$ as the marginal utility of income: 

$$\lambda = \frac{\partial u}{\partial x_\l} \frac{1}{p_\l} = \frac{\partial u}{\partial x_\l} \frac{\partial x_\l(p,w)}{\partial w}$$
Here we use an [[Envelope Theorem]]-type result. If I am maximizing utility, that means I must be indifferent between the marginal expenditure on any good. Given a tiny amount of money I can spend it anywhere. So if $e_\l$ is expenditure on good $\l$ that means $\frac{\partial e_\l}{\partial w} = \frac{\partial e_k}{\partial w}$ So then given an additional dollar, spending on $x_\l$ will be $1/p_\l$, so $1/p_\l$ is simply $\partial x_\l(p,w)/\partial w$. 
