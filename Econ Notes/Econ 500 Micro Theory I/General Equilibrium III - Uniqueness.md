---
aliases:
creation date: 2022-11-27 16:46
date updated: 2022-11-27 16:46

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[General Equilibrium III - Uniqueness]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

It's nice to have just the one WE. But it's not always straightforward to get uniqueness - in fact there are particular conditions required. But we can get local uniqueness. When?  Intuitively, we want to have something like $z(p)$ not touching $0$ in more than one place at a time. 

## Local Uniqueness

Let $\hat z(p)$ be the $L-1$ length excess demand vector that suffices to determine equilibrium. Let $D\hat z(p)$ be the $L-1 \times L-1$ vector of derivatives of $\hat z$. An equilibrium price vector $p_1, \ldots, p_{L-1}$ is <font color=gree>regular</font> when $D\hat z(p)$ is invertible. If every equilibrium price vector is regular, we have a regular economy. 

If a price vector is regular, it is locally unique: that is, there is some ball of radius $r > 0$ such that $p \in Br$ and $p \neq p^*$ means $z(p) \neq 0$. 
Proof: this is a consequence of the [[Implicit Function Theorem]]. The nonsingularity of $D \hat z$ means that, for some ball $U$ around $p^*$ and ball $V$ around $0$, there is a function $h: V \to U$ such that $u \in U \implies u = h(\hat z(u))$. 
