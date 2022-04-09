---
date updated: 2021-06-30 11:59

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes/econ/econ1123'
---

## [[1123 Class 2 - Intro to Sampling, Normal Distribution and Parameter Estimation]]
Part of [[@Econ 1123 Index]]


### Population and Density

Imagine the population of all workers in Boston - maybe about 300k people. We want to estimate $X$ - their annual income. Suppose you have a "master file" - a list of everyone in the population with a phone number. You could call everyone and get their income- a <font color=gree>census</font>. 

If you were to create a frequency histogram of these incomes, and draw an upper envelope of that histogram, you could approximate the ==density== of $X$. 

The [[Probability - Density and Mass|density]], or probability density function (PDF) is a function that maps from intervals of a random variable $(x_1, x_2)$ to measures in probability space $M$. The measure of $M$ tells us the probability that a draw from $X$ will land between $x_1$ and $x_2$. 

Practically speaking, the density of random variable $X$ is a function $f_X(x)$ such that 

$$\int_a^b f_X(x)dx = P(a < x < b) $$
$$\int_{-\infty}^{\infty} f(x)_Xdx = 1 $$

There are numerical ways to get densities from a dataset (such as [[kernel estimation]]).

A related function is the ==cumulative distribution function==, or CDF. The CDF $F_X$ is defined as:

$$ F_X(a) = \int_{-\infty}^a f_X(x)dx$$

This is the cumulative probability that a draw from $X$ will be at or below $a$. 

### Normal Distribution

One of the most important distributions is the normal distribution. Why is it so important?

- It crops up a lot in random places - human height in populations seems to be normally distributed, as are the circumferences of trees in a forest. 
- More importantly, the [[Central Limit Thm and Law of Large Numbers|Central Limit Theorem]] tells us that our estimators are normally distributed. 

The normal distribution is a symmetric bell shape. It's described by the mean $\mu$, the center of the bell, and the standard deviation $\sigma$, which gives the width of the bell. If $X$ is normally distributed, we write $X \sim \mathcal{N}(\mu, \sigma)$.

We sometimes talk about a "standard normal", which is $\mathcal{N}(0, 1)$; centered at $0$ with a standard deviation of $1$. There are tables of the standard normal in most statistics and econometrics books, which evaluate the CDF for various values of $x$. 

![[Pasted image 20210630193507.png]]
A normal bell shape

```ad-info
title: Normal Distribution Formulas

The PDF of the normal distribution is denoted by $f(x)$. For mean $\mu$ and standard deviation $\sigma$:

$$f(x) = \frac{1}{\sigma \sqrt{2\pi}} \; \text{exp}\left[ -\frac{1}{2}\left( \frac{x - \mu}{\sigma}\right)^2\right]$$

The PDF of the standard normal is usually called $\varphi(x)$. 

$$ \varphi(x)=  \frac{\text{exp}\left( -x^2/2\right)}{\sqrt{2\pi}} \;  $$

```

#### Z-scores and the Standard Normal


- If $X \sim \mathcal{N}(\mu, \sigma)$, then $z(X) \sim \mathcal{N}(0, 1)$, where $z(x) = (x - \mu)/\sigma$. 
- This latter is the $z$-score formula.
- For the standard normal, the $z$-score of $x$ is simply $x$ itself. 

Therefore, given any normally distributed variable, if we want to evaluate the CDF of any value, we can compute the $z$-score and then use the $z$ table to look up the value. 

The $z$-scores that map to a $5\%$ and $95\%$ cumulative probability are $\pm 1.96$. 


### Sampling Distribution

We return to our example of the 300,000 Boston workers, with their income distributed according to $X$. We can easily determine $\mu_X$ and $\sigma_X$ from a census. But censuses(?) are very expensive. So we want to sample a random subset of the workers and guess the parameters based on the sample. 

For large enough sample size $n$, the sample mean $\bar{x}$ approaches the population mean - we know this from the [[Law of Large Numbers]]. We treat $\bar{x}$ as an estimator of $\mu_X$. It's very unlikely that $\bar{x}$ will exactly equal $\mu_X$; we call the diference ==sample error==. We want to minimize sample error. But we don't know the true $\mu_X$. 

Suppose that you can keep drawing (with replacements) samples of size $n$. For each sample, you'll get another $\bar{x}$. As we do this over and over, the histogram of those $\bar{x}$ describes the density of a distribution.^[This process of resampling over and over is called [[Monte Carlo Simulation.]]] This distribution is called the ==sampling distribution==. 

The sampling distribution varies with $n$. For small $n$, it will approach the distribution of the underlying variable. However, as $n$ grows large, the [[Central Limit Thm and Law of Large Numbers|Central Limit Theorem]] tells us that $\bar{x}$ becomes normally distributed with mean $\mu_X$ - more tightly distributed as $n$ gets bigger. This is true for all distributions of underlying $X$, making the CLT an extremely useful result. 

We can describe the bias of an estimator $\overset{\approx}{x}$  as $E(\overset{\approx}{x}) - \mu_X$. The quality of being centered on $\mu_X$ means that $\bar{x}$ is an ==unbiased== estimator of $\mu_X$. 

The variance of the sampling distribution is $\sum (\bar{x}- \bar{\bar{x}})^2/(n-1)$. The square root of that is an estimator of sampling error. 

#### Sampling distribution in practice

Resampling over and over is also too costly to do. So we need to figure out a way to get at the sampling distribution from just one sample. 

It turns out we can do this <font color="red">why??</font> based on one sample. Our $\bar{x}$ is an unbiased estimator of $\bar{\bar{x}}$. We know the standard deviation of $\bar{x}$ is $\sigma_X/\sqrt{n}$. <font color="red">why??</font> We don't know $\sigma_X$, but we can estimate it with $s_x$, our sample standard deviation. So $s_x/\sqrt{n}$ is an estimator for the standard deviation of $\bar{x}$ - we can write $\widehat{\text{SD}(\bar{x})}$ (the hat means estimation)

The estimate of the sampling error of the estimate is called the ==standard error==. This is crucial for hypothesis testing. 

In summary - the [[Central Limit Thm and Law of Large Numbers|Central Limit Theorem]] tells us that, as $n$ grows larger, $\bar{x} \sim \mathcal{N}(\mu_X, \sigma_X/\sqrt{n})$.


<font color="red"> Discussion of hypothesis testing from this class moved to next class for coherence. </font>