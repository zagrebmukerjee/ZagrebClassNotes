---
aliases:
creation date: Saturday, October 8th 2022, 3:56 pm
date updated: Saturday, October 8th 2022, 7:13 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Econometrics VII - Sampling]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 550 Index]]

## Setup

A <font color=gree>sample</font> of size $n$ is some random variables/vectors, $X_1, \ldots, X_n$. The sample is a <font color=gree>random sample</font> if the $X_i$ are i.i.d. - independent and identically distributed. 

The joint density of the sample is $f(x_1, \ldots, x_n)$, or $f_{X_1, \ldots, X_n}(x_1,\ldots, x_n)$. If iid, then 
$$ f_{X}(x) = \prod_{i=0}^n f_{X_i}(x_i)$$by independence.


A <font color=gree>statistic</font> is any *known* function of the sample - ie. a function that can be evaluated as soon as a sample is realized. The sample mean, sample standard deviation etc. are statistics. 

```ad-note
title: 

As an aside, the sample mean $\overline X_n$ is $\arg \min_{b} \sum_{i=0}^n (X_i - b)^2$. So it's a least-squares estimator. 


```

## Sample Mean and Variance

The expectation of the sample mean in the case of a random sample: Let $X_i$ be iid with mean $\mu_{X_i} = \mu$ and variance $\sigma^2$

$$ E\overline X_n = E\left[\frac{1}{n}\sum_{i=1}^n X_i\right] = \frac{1}{n} \sum_{i=1}^n EX_i = \mu$$
Note that if $X, Y$ are independent, then $E[XY] = EXEY$. 

The variance is 
$$\begin{align}
\var(\overline X_n) &= E[(\overline X - E\overline X)^2]\\
&= E[\overline X^2] - \mu^2\\
&= E\left[ \frac{1}{n}\sum_{i=1}^n X_i \right]^2 - \mu^2\\
&= \frac{1}{n^2} E\left[\sum_{i=1}^n\sum_{j=1}^nX_iX_j \right] - \mu^2\\
&= \frac{1}{n^2} E\left[\sum_{i=1}^n\sum_{j=1}^n X_iX_j \right] - \mu^2\\
&= \frac{1}{n^2} \left(E\left[\sum_{i=1}^n X_i^2\right] + E\left[n(n-1)\mu^2 \right]\right) - \mu^2\\
&= \frac{E\left[\sum_{i=1}^n X_i^2\right]}{n^2} - \frac{ n\mu^2}{n^2}\\
&= \frac{E\left[\sum_{i=1}^n X_i^2- \mu^2\right]}{n^2} \\
&= \sigma^2/n
\end{align}$$
