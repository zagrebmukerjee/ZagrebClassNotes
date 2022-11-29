---
aliases:
creation date: Sunday, November 27th 2022, 4:45 pm
date updated: Monday, November 28th 2022, 2:59 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[General Equilibrium IV - Uniqueness]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 500 Micro Theory Index]]

It's nice to have just the one WE. But it's not always straightforward to get uniqueness - in fact there are particular conditions required. But we can get local uniqueness. When? Intuitively, we want to have something like $z(p)$ not touching $0$ in more than one place at a time. 

## Local Uniqueness

Let $\hat z(p)$ be the $L-1$ length excess demand vector that suffices to determine equilibrium. Let $D\hat z(p)$ be the $L-1 \times L-1$ vector of derivatives of $\hat z$. An equilibrium price vector $p_1, \ldots, p_{L-1}$ is <font color=gree>regular</font> when $D\hat z(p)$ is invertible. If every equilibrium price vector is regular, we have a regular economy. 

#### Proof
If a price vector is regular, it is locally unique: that is, there is some ball of radius $r > 0$ such that $p \in Br$ and $p \neq p^*$ means $z(p) \neq 0$. 
Proof: this is a consequence of the Inverse Function Theorem, aka the [[Implicit Function Theorem]]. The nonsingularity of $D \hat z$ means that, for some ball $U$ around $p^*$ and ball $V$ around $z(p^*) = 0$, there is a bijective function $h: V \to U$ such that $u \in U \implies u = h(\hat z(u))$. 

Now suppose $p \in U$ is an equilibrium, i.e. $\hat z(p) = 0$. Then $p = h(z(p))$ means $p = h(0)$; but $p^* = h(0)$, and $h$ is a bijection, so $p = p^*$. 

Define the equilibria of an economy as the set $E = \{ p \in \R^{L-1}_{++}\big| \hat z(p) = 0 \}$. Then each $p \in E$ is locally unique: this means $E$ is closed. For all $p$, if $z(p) =0$ then we have shown that prices cannot be arbitrarily small (since that means that $z$ goes to infinity). So there's some $r$ such that $p \in [r\inv, r]^L$. Thus $E$ is bounded. And a closed, bounded discrete set in $\R^{L-1}$ is finite (an open subcover is simply a ball around each point). 


## Genericity Analysis

Suppose $v$ has $n$ elements, and $f(v)$ has $m$. We can make a system of $m$ equations: $f(v) = 0$. Generally, if $M > N$ there are 'too many' equations and probably no solution; if $M < N$ 'too few' equations and probably too many solutions (overdetermined/underdetermined). So $M=N$ is the Goldilocks region. 

When is this actually the case? Well, we need independence at the solutions. We call the system $f(v)=0$ <font color=gree>regular</font> if rank $Df(v) = M$ when $f(v) = 0$. 
