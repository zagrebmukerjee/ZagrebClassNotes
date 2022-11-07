---
aliases:
creation date: 2022-11-07 12:48
date updated: 2022-11-07 12:48

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Estimation IIIa - Point Estimation]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 550 Index]]

We're now interested in point estimation - the specific values of $\theta_0$. We say that $\hat\theta_n$ is an <font color=gree>unbiased</font> estimator of $\theta_0$ if $E_\theta\hat\theta_n = \theta$ for all $\theta \in \Theta$. where $\Theta$ is the parameter space. When it's not unbiased, the bias is $E_\theta \hat\theta_n - \theta$. Unbiasedness is a desirable criterion - not the only one, since given two equally (un)biased estimators one prefers the less biased. 

## Unbiased Minimum Variance Estimator

A (lexicographic) preference across estimators can be expressed with the UMVU criterion: an estimator $\hat\theta^*$ is UMVU if 
1) $E_\theta\hat\theta^* = \theta$ for all $\theta \in \Theta$, and 
2) $\var_\theta(\hat\theta^*) \lew 