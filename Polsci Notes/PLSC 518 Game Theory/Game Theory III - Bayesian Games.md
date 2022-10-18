---
aliases:
creation date: Tuesday, October 4th 2022, 3:35 pm
date updated: Tuesday, October 18th 2022, 4:44 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Game Theory III - Bayesian Games]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

![[Game Theory II - Equilibrium#Problem Formulation]]

We all know each others' costs, and we all know that we know etc. 







# Scratch

Second price auctions we did. 

First price auction. Uniformly distributed valuations on $[0,1]$.

Strategy for 1. What's the probability I win with bid x? Assume that $b(v)$ is strictly increasing for other players (this could be shown). 

It's $P(b_2, \ldots, b_{n-1} < x)$. What's the probability that $P(b_i(v_i) < x)$ for any given $i$? Rearrange the condition to say $v_i < b\inv(x)$. I know the distribution of $v_i$. 

Two ways to approach this. 
1) easier but requires guessing
2) longer no guessing

Suppose I can say that $P(1 \text{ wins with bid } x)$ = $(x/q)^{n-1}$. Then I have $\max_x EU_1 (x, v) = (v-x)(x/q)^{n-1}$. Differentiate to get $-(x/q)^{n-1} + (v-x)(n-1)(x/q)^{n-2}/q = 0$. 
$x = v/[n/(n-1)]$


If everyone else is playing a linear strategy, I want to play one too. I don't care about their coefficients, incidentally. So this looks like a great equilibrium. 


### Generalized

First price auction: $v_i \sim F()$ on $\R+$. $F$ differentiable and $n$ arbitrary. Assume $b(v)$ is increasing (strictly). 

$$EU = \max_x (v-x)F[b\inv(x)]^{n-1}$$ I also need to find that $b(v) = x$, since this could be symmetric. 
$$\begin{align}
0 &= (v-x)(n-1)f[b\inv(x)]^{n-2}[1/b'(b \inv(x))] - F[b\inv(x)]^{n-1}\\
F[b\inv(x)]^{n-1} &= (v-x)(n-1)F[b\inv(x)]^{n-2}f[b\inv(x)][1/b'(b \inv(x))]
F[b\inv(b(v))]^{n-1} &= (v-b(v))(n-1)F[b\inv(b(v))]^{n-2}f[b\inv(b(v))][1/b'(b \inv(b(v)))]
\end{align}$$


 
