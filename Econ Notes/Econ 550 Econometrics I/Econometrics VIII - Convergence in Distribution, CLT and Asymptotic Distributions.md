---
aliases:
- "CLT"
- "Central Limit Theorem"
creation date: Sunday, October 30th 2022, 9:44 am
date updated: Friday, November 4th 2022, 10:55 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Econometrics VIII - Convergence in Distribution, CLT and Asymptotic Distributions]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Convergence in Distribution

Convergence in probability describes, loosely, a density collapsing to a spike over a point. Convergence in distribution describes a density coverging to another density. This will be useful for us to talk about the asymptotic distribution of sample statistics. After all, we know that the sample mean is converging to a spike. But how long will it take to get there? And what will it look like on the way?

### Definition

We say that some random variable sequence $X_n$ <font color=gree>converges in distribution</font> to $X$ if: 

$$\lim_{n \to \infty} P(X_n \leq x) = P(X \leq x)$$
or 
$$ \lim_{n \to \infty} F_{X_n}(x) = F_{X}(x)$$
wherever $F_X()$ is continuous. We can also write $X_n \to_d X$. 
- If $X$ has some distribution, we can describe that as the <font color=gree>asymptotic distribution</font> or <font color=gree>limiting distribution</font> of $X_n$. 
- If $X \sim \mathcal N(0,1)$, for instance, we can write also $X_n \to_d \mathcal N(0, 1)$. 

### Properties/Lemma 1
Suppose $Y_n \to_d Y$ and $Z_n \to_p z$. Then:
1) $Y_n + Z_n \to_d Y + z$
2) $Y_nZ_n \to_d zY$
3) $Y_n/Z_n \to_d Y/z$ where $z \neq 0$. 

For 1): We want to show that $\lim_{n\to\infty} P(Y_n + Z_n \leq a) = P(Y + z \leq a)$. $P(Y_n + Z_n \leq a) = P(Y_n + (Z_n -z) \leq a -z )$. But as $n \to \infty$, $Z_n - z \to 0$; so $P(Y_n + (Z_n - z) \leq a-z) \to P(Y_n \leq a -z) \to P(Y \leq a -z)$. 

For 2) consider the asymptotic distribution of $Y_n Z_n - Y_n z = Y_n (Z_n - z)$. This converges to $0$ at all points of continuity of $Y$. So $Y_nZ_n \to_d zY$. For 3, a similar argument applies (let $W_n = 1/Z_n$). 


## Central Limit Theorem

Let $X_1, \ldots, X_n$ be i.i.d. random variables with mean $\mu$ and positive variance $\sigma^2$. Then 
$$P(\sqrt{n}[\overline X_n - \mu]/\sigma\leq a) \to P(Z \leq a)$$
where $Z \sim \mathcal N(0,1)$. The $\sqrt{n}$ term is there because $\bar X_n - \mu$ collapses, so we can't talk about its nontrivial asymptotic distribution. But we can normalize it and talk about the normalized quantity. 

We can also write this as 
$$ P(\sqrt{n}[\overline X_n - \mu) \leq a) \to P(\tilde Z \leq a)$$
where $\tilde Z \sim \mathcal N (0, \sigma^2)$.
Another way: 
$$\frac{\overline X_n - \mu
}{\sigma/\sqrt{n}}\to_d \mathcal N(0,1)$$
### Proof

#status/section/🚧 


``` ad-note
title: Application of Convergence in Distribution
As one extension of the CLT: Suppose $\sigma_X$ is unknown. Then can we look at $\sqrt{n}\frac{\overline X_n - \mu}{S_{Xn}}$?
Yes: 

$$\begin{align}
\frac{\sqrt{n}(\overline X_n - \mu)}{S_{X_n}} &= 
\frac{\sqrt{n}(\overline X_n - \mu)/\sigma}{S_{X_n}/\sigma}\\
S_{Xn}/\sigma &\to_p 1 \\
\sqrt{n}(\overline X_n - \mu)/\sigma &\to_d Z \sim N(0,1)\\
\frac{\sqrt{n}(\overline X_n - \mu)/\sigma}{S_{X_n}/\sigma} &\to_d Z\\
\frac{\sqrt{n}(\overline X_n - \mu)}{S_{X_n}} &\to_d Z\\
\end{align}$$

Here I use Slutsky's theorem and Lemma 1 part c. 
```

## Multivariate CLT

#### Cramer-Wold Device (Lemma)

Let $Y_n$ be $k \times 1$ vectors. If $c'Y_n \to_d c' Y$ for all $c \in \R$ then $Y_n \to Y$. In other words, if every linear combination of elements of the $Y_n$ converges to the same linear combination of elements of $Y$, then the original vectors also converge to $Y$. Proof involves characteristic function convergence of $c'Y_n$. 

#### Multivariate CLT Construction

We will use this to generate a multivariate CLT. Suppose we have some random vectors $Y_n$ that are i.i.d with $\mu$ and $\Sigma$. Then $c'Y_n$ are random scalars that are i.i.d. By the linearity of expectation, $Ec'Y_n = c'EY_n = c' \mu$. The variance is $\var (c'Y) = c'\Sigma c$. 

Then from the regular CLT we know that $\sqrt{n}(c' \overline Y_n - c' \mu) \to_d N(0, c' \sigma^2 c)$. 
It follows that $c' \sqrt{n}(\overline Y_n - \mu) \to_d c' N(0, \sigma^2)$ and so, by the Cramer-Wold Device, $c' Y_n \to_d c'Y$, then $Y_n \to Y$. 


## Continuous Mapping Theorem

We have two tools that will help us like Slutsky does. First the CMT.

If $Y_n \to_d Y$ are all $m \times 1$ and $h:\R^m \to \R^p$ continuous at all $y$ in the support of $Y$, then
$$ h(Y_n) \to_d h(Y) \text{ as } n \to \infty$$

#### Proof

Limited to the scalar case, and $h$ strictly increasing and continuous on $\R$. Suppose $F_{h(Y)}$ continuous at $b$. Then, 

$$\begin{align}
\limn P(h(Y_n) \leq b) &= \limn P(h\inv[h(Y_n)] \leq h\inv(b))\\
&= \limn P(Y_n \leq h\inv(b)) \\
&= \limn P(Y \leq h\inv(b)) \\
&= \limn P(h(Y) \leq b) \\
\end{align}$$
Great success.

This is useful, for instance, to see that: 

$$\begin{align}
\frac{\sqrt{n}(\Xbar_n - \mu)}{S_{Xn}} &\to_d N(0,1) \implies \\
\frac{n(\Xbar_n - \mu)^2}{S^2_{Xn}} &\to_d \chi^2_1 \\
\end{align}$$
Can also use this for Lemma 1 above, with Lemma 3:

If $Y_n \to_d Y$ and $Z_n \to_p r$ then 

$$\begin{pmatrix} Y_n \\ Z_n \end{pmatrix} \to_d \begin{pmatrix} Y \\ r\end{pmatrix}$$


## Application: Asymptotic Distribution of Sample Variance


We want to know the asymptotic distribution of the sample variance. A good candidate for appropriate renormalization is $\sqrt{n}(\hat S_{Xn} - \sigma^2)$, since we know that $\hat S_{Xn} \to_p \sigma^2$. Assume $EX^4$ finite.

Then rewrite:
$$\begin{align}
\hat S_{Xn} &= n\inv \sumn{i} (X_i - \Xbar_n)^2 \\
&= n\inv \sumn{i} X_i^2 - 2\Xbar_n X_i + \Xbar_n^2 \\
&= n\inv \sumn{i} X_i^2 + + 2X_i \mu + \mu^2 - 2X_i \mu - \mu^2 - 2\Xbar_n X_i + \Xbar_n^2 \\
&= n\inv \sumn{i} [X_i^2 + + 2X_i \mu + \mu^2] - n\inv \sumn{i} [2X_i \mu] - \mu^2 - n\inv\sumn{i}[ 2\Xbar_n X_i] + \Xbar_n^2 \\
&= n\inv \sumn{i} [X_i^2 + + 2X_i \mu + \mu^2] - n\inv \sumn{i} [2\Xbar_n \mu - \mu^2 - \Xbar_n^2]\\
&= n\inv \sumn{i}(X _i - \mu)^2 - (\Xbar_n - \mu)^2\\
\end{align}$$
Then: 
$$\begin{align}
\sqrt{n}(\hat S_{Xn} - \sigma^2) &= \sqrt{n}\inv \left[\sumn{i}(X _i - \mu)^2 - (\Xbar_n - \mu)^2 - \sigma^2\right]\\
&= \left[\sqrt{n}\inv \sumn{i}[(X _i - \mu)^2 - \sigma^2] - \sqrt{n}\inv \sumn{i}(\Xbar_n - \mu)^2 \right]\\
\end{align}$$

Let $W_i = (X_i - \mu)^2$. Then $W_i \to_p \sigma^2$. 
$$\begin{align}
\sqrt{n}(W_i - \sigma^2) &= N(0, \var(W_i))\\
\sqrt{n}(W_i - \sigma^2) &= N(0, \var(X_i - \mu)^2)\\
\end{align}$$
$\var(X_i - \mu)^2$ being finite relies on our assumption on $EX^4$ above. 

The term we have left is $\sqrt{n}\inv \sumn{i}(\Xbar_n - \mu)^2 = \sqrt{n} (\Xbar_n - \mu)^2$. But $(\Xbar_n - \mu) \to_p 0$, and $\sqrt{n}(\Xbar_n - \mu) \to_d N(0,1)$. So by Lemma 1: 
$$ (\Xbar_n - \mu) \sqrt{n} (\Xbar_n - \mu) = X_iY_i$$
where $X_i \to_p 0$ and $Y_i \to_d$ something. SO this all goes to $0$. 

Then the asymptotic distribution of $\hat S_{Xn}^2$ is $N(0, \var(X_i - \mu)^2)$. Asymptotically, the distribution of $S_{Xn}^2$ is the same. 



## Delta Method

This is another tool for finding out what something converges to in distribution. It's a sort of Slutsky analogue in the same way the CMT was. Let $g()$ be continuous from $\R \to \R$ continuously differentiable at $\theta_0$. Let $\hat \theta_n$ be an estimator of $\theta_0$. Then:

$$ \sqrt{n}(g(\hat\theta_n) - g(\theta_0)) \to_d N(0, g'(\theta_0)^2\sigma^2) $$
In a multivariable analogue, let $g: \R^n \to \R^m$, and $\theta_0, \hat \theta_n$ be $n\times 1$ vectors. 
