---
aliases:
creation date: Friday, November 4th 2022, 11:14 am
date updated: Friday, November 4th 2022, 11:29 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Estimation II - Intervals]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

[[Econ 550 Index]]

I'm interested in some parameter $\theta_0$, unknown. I want to construct an 'interval estimator' - that contains $\theta_0$ with some given probability $1- \alpha$ (eg. $95\%$). Call $1-\alpha$ the confidence level. 

```ad-warning
title: Subtleties of the Confidence Interval Definition

Any confidence interval is a realization of this interval estimator evaluated at some particular sample. So it is nonrandom; either it contains $\theta_0$ or it doesn't. The probability here is over repeated sampling. 

```

One straightforward way is to take some estimator $\hat \theta$ and center on it with some constant: 
$$
\hat\theta \pm \frac{c}{\sqrt{n}}$$What's the right $c$? (The $\sqrt{n}$ term is mostly for convenience so that we can have an $n-$invariant $c$. 

Our criterion is :

$$ P\left(\theta_0 \in \left[\hat \theta - \frac{c}{\sqrt{n}}, \hat \theta + \frac{c}{\sqrt{n}} \right] \right) \geq 1-\alpha$$
Then we can transform this to 
$$ P\left(|\sqrt{n}(\hat \theta - \theta_0)| \leq c\right) \geq 1-\alpha $$
