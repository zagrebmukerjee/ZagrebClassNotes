---
aliases:
creation date: 2022-11-18 14:51
date updated: 2022-11-18 14:51

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Estimation V - Generalized Method of Moments]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 550 Index]]


## Intro

Recall: a $k$th moment of RV $X$ is $E(X^k)$. 

We estimated $E(X)$ with $n\inv \sumn{i} X_i$. More generally, WLLN can be used to show that $n\inv \sumn{i} X_i^k$ is a consistent estimator of the $k$th moment. 

This is a special case of the method of moments. MM operates by analogy - if we know/suppose/believe there is some condition on the population, like $E(X) = \mu$, we can then come up with a sample analogue, in this case $\Xbar = n\inv \sumn{i}X_i$. We know this is the case because of the [[Econometrics VII - Sampling and Convergence in Probability|WLLN]]. 

Generally the analogy principle is saying $E[f(x)] = n\inv \sumn{i} f(x_i)$. 

If I have 2 moment conditions, eg $E(X) = \mu$ and $E[X^2] = \sigma^2 + \mu^2$, and 2 analogies, then I have something well identified - there is a precise estimation. 

But if I say that eg. $E[x^4] = 3\sigma^4$, then this becomes troublesome, with more moment conditions than parameters. This is when I want to use a GMM - to get as close as I can. 


### Motivation

- It's less parametric. Don't have to choose a family of distributions; sufficient to establish moment conditions. 
- Robust to distribution assumptions eg. heteroskedasticity
- deals with nonlinearity 
- asymptotic consistency


## Method


Suppose that $X \sim N(\mu, \sigma^2)$. Then we have two moment conditions on the true $X$: $E[X] = \mu$ and $\var(X)