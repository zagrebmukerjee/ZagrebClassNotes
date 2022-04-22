---
date updated: 2021-06-23 15:27

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
---

### [[Central Limit Thm and Law of Large Numbers]]

Drawn from Stat 110 lecture here

https://www.youtube.com/watch?v=OprNqnHsVIA

Let $x_1, \ldots$ be iid with mean $\mu$ and variance $\sigma^2$.
These theorems tell us what happens with sampling from this population.

$\bar{x}_n$ is the sample mean of a sample with size $n$.  What can we say about it?

#### Law of Large Numbers: Intro

$\bar{x}_n$ converges to $\mu$ as $n \to \infty$ with probability 1 - that is to say, the sample mean (a random variable) converges to the true mean (a constant).

What is the limit of a random variable? For each value of $\bar{x}$, those values converge to $\mu$.  

Eg. What if $x_j \sim \text{Bernoulli}(p)$. Infinite sequence of coin tosses where prob of heads is $p$.

Add up all these Bernoullis $1-n$ - converges to $p$ with probability $1$.  Probability $1$ means that we can't say it's _impossible_ to flip HHHH... forever, but it won't happen. This is a result underpinning all parameter estimation. 

This is **not** the gambler's fallacy - I got tails 10 times in a row on a fair coin, I'm due for heads. The coin is memoryless. It works through "swamping" - the 10 tails in a row will be swamped as $n$ gets incredibly large relative to 10. 

Note: iid is a very important property here. And a lot of things are not iid. 

#### Weak Law of Large Numbers

Says something less than the above. 

For any $C >0$, probability $P(|\bar{x}_n - \mu | > C) \to 0$ as $n \to \infty$. This is just a way of saying that as $n$ gets large, $\bar{x}_n$ goes towards $\mu$. 

We use [[Markov's and Chebyshev's Inequalities#Chebyshev's Inequality|Chebyshev's Inequality]] here: 

$$P(|\bar{x}_n - \mu) > C) \leq \frac{\text{Var}(\bar{x}_n)}{C^2}$$

So what is variance of $\bar{x}_n$? 

$$\text{Var}(\bar{x}_n) = \frac{1}{n^2} (n \sigma^2) = \frac{\sigma^2}{n}$$

$$P(|\bar{x}_n - \mu) > C) \leq \frac{\sigma^2}{C^2 n}$$

As $n \to \infty$ that goes to zero. 

#### Central Limit Theorem

So we know that $\bar{x}_n$ goes to $\mu$. But what does the distribution of $\bar{x}_n$ look like? And how fast does it approach?

For how fast - can see by multiplying by something that goes to $\infty$ at a known rate, letting us bound our thing's rate.

We're going to use $n^C(\bar{X}_n - \mu)$ to create upper and lower bounds on our convergence. Magic threshold for $C$ will be $1/2$. 

The central limit theorem is:
$$\lim_{n \to \infty} n^\frac{1}{2}\frac{\bar{X}_n - \mu}{\sigma} \to \mathcal{N}(0,1)$$

The former converges in distribution. (what is that?)

```ad-info
title: Why do we care?
collapse: true
This is cool because it's a super general result. We assumed very little to get here. But out comes the standard normal. 

This can be used to justify normal approximations (why?)
```

Equivalent to the left side:

$$\frac{\sum x_j - n\mu}{\sqrt{n}   \sigma}$$

Assume that MGF ([[moment-generating function]]) of $x_i$ exists. 

It suffices to show that the MGFs converge to the normal's MGF (a homework problem). 

Assume WLOG that $\mu = 0$ and $\sigma = 1$ (since we can un-standardize). Let $S_n$ be the sum of the first $n$ terms. We want to show that MGF of $S_n/\sqrt{n}$ goes to 0. 

What is that MGF? It's  $E(e^{tS_n/\sqrt{n}})$
