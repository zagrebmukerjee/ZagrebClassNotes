---
aliases:
- "Convergence in Probability"
- "Convergence in Distribution"
- "Law of Large Numbers"
- "Weak Law of Large Numbers"
- "LLN"
- "WLLN"
- "Slutsky Theorem"
- "Sample Mean"
- "Sample Variance"
creation date: Sunday, October 9th 2022, 11:00 am
date updated: Sunday, October 30th 2022, 9:39 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/stats/theory'
- '#topics/methods'
---

# [[Econometrics VII - Sampling and Convergence in Probability]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## Sampling

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

### Estimators

More generally, I can have so


## Convergence in Probability

First of two forms of convergence that are useful for characterizing sample statistic behavior. 


### Definitions

Suppose a sequence of random variables $X_n$, and a constant $c$. Then we can say that $X_n$ <font color=gree>converges in probability</font> to $c$ if, for all $\epsilon$, 

$$\lim_{n\to \infty} P(|X_n - c| > \epsilon) = 0 $$
Equivalently, 

$$\lim_{n\to \infty} P(|X_n - c| < \epsilon) = 1 $$

Notation: if $X_n$ converges in probabilty to $c$ we can say
$$\begin{align}
X_n \to_p c\\
\plim{n\to\infty} X_n = c
\end{align}$$

### Property 1
Suppose $\plim{n \to \infty} Y_n = c$. Then for some constant $b$, 
$$ \plim{n\to\infty} bY_n = bc$$
#### Proof:
We know that for any $\epsilon$, $\lim_{n\to \infty} P(|X_n - c| > \epsilon) = 0$. It follows that $\lim_{n\to \infty} P(|X_n - c| > \epsilon/|b|) = 0$; which means that $\lim_{n\to \infty} P(|bX_n - bc| > \epsilon) = 0$. This doesn't work for $b=0$ but then the result is trivial. 

### Property 2

Suppose $\plim{n \to \infty} X_n = a$ and $\plim{n \to \infty} Y_n = b$. Then 

$$ \plim{n \to \infty} X_n + Yn = a + b$$
#### Proof:

Recall triangle inequality: $|a + b| \leq |a| + |b|$. 
If $a + b > c$, then either $a > c/2$ or $b> c/2$ (or both). 
$$\begin{align}
P(|X_n + Y_n - a - b| > \epsilon) &= P(|X_n - a + Y_n - b| > \epsilon)\\
&\leq P(|X_n - a| + | Y_n - b| > \epsilon) \\ 
&\leq P(|X_n - a| > \epsilon/2 \lor | Y_n - b| > \epsilon/2) \\
&\leq P(|X_n - a| > \epsilon/2) + P( | Y_n - b| > \epsilon/2) \\
&\to 0 \text{ as } n \to \infty
\end{align}$$
### Property 3
If $\plim{n \to \infty} Y_n =c$ and $\plim{n \to \infty} X_n = d$ 
then 
$$ \plim{n\to\infty} X_n Y_n = cd $$
$$ \plim{n\to\infty} X_n/Y_n = c/d $$ the latter only if $d \neq 0$

Proof: this follows from the Slutsky theorem. 

## Weak Law of Large Numbers

Assume again that $X_i$ are iid. Recall that $\var(\overline X_n) = \sigma^2_X/n$; that is, as $n$ increases, $\overline X_n$ becomes less and less dispersed around its mean. That mean is the 'true' parameter value $\mu_X$. 

A formalization of this intuition: 

Suppose $\{ X_i: i \geq 1\}$ a sequence of random variables, i.i.d., with $E|X| < \infty$. Define $\overline X_n = n\inv \sum_{i=1}^n X_i$. Let $\mu_X = E[X_1]$. For all $\epsilon > 0$, 

$$ \lim_{n\to\infty} P(|\overline X_n - \mu_X| > \epsilon) = 0 $$
This is the same as saying that $\overline X_n \to_p \mu_X$, i.e. $\overline X_n$ [[Econometrics VII - Sampling and Convergence in Probability|converges in probability]] to $\mu_X$. 

#### Proof
For convenience, fix $\sigma_X^2$ finite. The proof will generalize. 
Use [[Markov's and Chebyshev's Inequalities|Chebyshev's Inequality]], with $Y = \overline X$ and $k = \epsilon\sqrt{n}/\sigma_X$. 

$$\begin{align}
P(|Y - Ey| > k\sigma_Y) & \leq \frac{1}{k^2}\\
P\left(\left|\overline X - \mu_X\right| > \frac{\epsilon \sqrt{n}}{ \sigma_X}\frac{\sigma_X}{\sqrt{n} }\right) & \leq \frac{1}{\frac{\epsilon^2n}{\sigma_X^2}}\\
P\left(\left|\overline X - \mu_X\right| >\epsilon\right) &\leq \frac{\sigma^2_X}{\epsilon^2 n}\\
0 < \lim_{n \to \infty} P\left(\left|\overline X - \mu_X\right| >\epsilon\right) &\leq \sigma^2_X \epsilon^2 \lim_{n \to \infty} \frac{1}{n}\\
\lim_{n \to \infty} P\left(\left|\overline X - \mu_X\right| >\epsilon\right) &= 0
\end{align}$$

In the last two lines I use the non-negativity property of probability, and the fact that $\sigma_X^2$ is finite. 

### Extension 1 of the WLLN

Suppose $\{X_i: i\geq 1\}$ are random variables that are NOT necessarily independent, but ARE uncorrelated/ have covariance $0$. Define $\overline X_n = n\inv \sum_{i=1}^n X_i$. 
If $EX_i^2 < \infty$ for each $i$, and $\sup_{i\geq 1}\var(X_i)< \infty$, then:

$$ \overline X_n - n\inv \sum_{i=1}^nEX_i \to_p 0$$
That is to say, the sample mean converges to the average mean of the sampled RVs. 
#### Proof
Define $\mu_i = EX_i$; $\overline \mu_n = n\inv \sum_{i=1}^n \mu_i$, $\sigma^2_i = \var(X_i)$. 
Recall [[Markov's and Chebyshev's Inequalities|Markov's Inequality]] - $P(|X| > k) \leq \frac{EX}{k}$. Let $X = (\overline X _n- \mu_n)^2$ and $k = \epsilon^2$. 

$$\begin{align}
P(|\overline X_n - \overline\mu_n| > \epsilon) &= P((\overline X - \overline\mu_n)^2 > \epsilon^2) \\
& \leq \frac{E(\overline X - \overline\mu_n)^2}{\epsilon^2}\\
&\leq \frac{E\left[ \sum_{i=1}\sum_{j=1}(X_i - \mu_i)(X_j- \mu_j)\right]}{n^2 \epsilon^2}\\
&\leq \frac{\left[ \sum_{i=1}\sum_{j=1}E(X_i - \mu_i)(X_j- \mu_j)\right]}{n^2 \epsilon^2}\\
&\leq \frac{\left[ \sum_{i=1}\sum_{j=1}\cov(X_i, X_j)\right]}{n^2 \epsilon^2}\\
&\leq \frac{\left[ \sum_{i=1}\var(X_i)\right]}{n^2 \epsilon^2}\\
&\leq \frac{\sup_{i\geq 1}\var(X_i)}{n \epsilon^2}\\
\end{align}$$
which falls off with $n$. 

This is extensible to a case when $\rho_{X,Y}$ is bounded. 


## Slutsky Theorem

Suppose $Y_n \to_p c$, a constant, as $n \to \infty$. Suppose some function $h()$ is continuous at $c$. Then
$$ h(Y_n) \to_p h(c)$$
This is a very useful result. For instance, I have shown that the sample variance converges in probability to the population variance. Does the sample standard deviation converge to the population sd? I could prove that too; or I could use Slutsky's theorem, observe that $\sqrt{x}$ is continuous for $x \geq 0$, and then get this result for much less work.

This result can be generalized to vector-valued functions, with length $|| \cdot ||$ replacing the absolute value. 

#### Proof
Proof relies on using continuity to squeeze $h(Y_n)$ and $h(c)$ together. 

We want to show that, for any epsilon,
$$ \lim_{n \to \infty} P(|h(Y_n) - h(c)|< \epsilon) = 1$$
$h$ is continuous at $c$: so, for any $\epsilon > 0$, there is some $\delta > 0$ such that $|a - c| <\delta \implies |h(a) - h(c)| < \epsilon$. But the fact that $Y_n \to_p c$ means that $\lim_{n\to\infty} P(|Y_n - c| <\delta) = 1$. So $P(|h(Y_n) - h(c)| < \delta) = 1$. 


```ad-note
An estimator $\hat \theta_n$ of $\theta_0$ is <font color=gree>consistent</font> when $\hat \theta_n \to_p \theta_0$. 

```


## Convergence in Distribution


Convergence in Distribution is a second type of convergence. Convergence in probability describes, loosely, a density collapsing to a spike over a point. Convergence in distribution describes a density coverging to another density. This will be useful for us to talk about the asymptotic distribution of sample statistics. After all, we know that the sample mean is converging to a spike. But how long will it take to get there? And what will it look like on the way?