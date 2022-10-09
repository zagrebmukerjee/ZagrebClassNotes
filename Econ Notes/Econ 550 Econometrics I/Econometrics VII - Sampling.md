---
aliases:
creation date: Saturday, October 8th 2022, 3:56 pm
date updated: Sunday, October 9th 2022, 10:58 am

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

### Mean

The expectation of the sample mean in the case of a random sample: Let $X_i$ be iid with mean $\mu_{X_i} = \mu$ and well defined variance $\sigma^2$

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
### Variance

Define a statistic $\hat S^2_X = n\inv \sum_{i=1}^n ( X_i - \overline X)^2$. 

Then
$$\begin{align}
E[\hat S_X^2 ] &= \frac{1}{n}E\left[\sum_{i=1}^n ( X_i - \overline X)^2\right] \\
&= \frac{1}{n}E\left[\sum_{i=1}^n [( X_i - \mu_X)+(\mu_X- \overline X)]^2\right] \\
&= \frac{1}{n}\sum_{i=1}^n E\left[ ( X_i - \mu_X)^2 +(\overline X - \mu_X )^2 -2(\overline X - \mu_X )(X_i-\mu_X) \right] \\\\
&= \frac{1}{n}\sum_{i=1}^n E( X_i - \mu_X)^2 +\frac{1}{n}\sum_{i=1}^n E (\overline X - \mu_X )^2 -\frac{2}{n}\sum_{i=1}^n E \left[\left(n\inv \sum_{j=1}^n (X_j) - \mu_X \right)(X_i-\mu_X) \right] \\
&= \sigma^2 +\sigma^2/n -\frac{2}{n} \sum_{i=1}^nE \left[\left(n\inv \sum_{j=1}^n (X_j - \mu_X) \right)(X_i-\mu_X) \right] \\
&= \sigma^2 +\sigma^2/n -\frac{2}{n}E \left[n\inv \sum_{i=1}^n\sum_{j=1}^n (X_j - \mu_X)(X_i-\mu_X) \right] \\
&= \sigma^2 +\sigma^2/n -\frac{2}{n}E \left[n\inv \sum_{i=1}^n\sum_{j=1}^n \cov(X_i,X_j) \right] \\
&= \sigma^2 +\sigma^2/n -\frac{2}{n}E \left[n\inv \sum_{i=1}^n\var(X_i,X_j) \right] \\
&= \sigma^2 +\sigma^2/n -2\sigma^2/n\\
&= \frac{(n-1)}{n}\sigma^2
\end{align}$$

We need a bias-correction, especially for smaller sizes. So define a <font color=gree>sample variance</font> as 
$$ S_X^2 = \frac{1}{n-1}\sum_{i=1}^n (X_i^2 - \overline X)^2 $$
Then $ES_X^2 = \sigma^2_X$. 


## 