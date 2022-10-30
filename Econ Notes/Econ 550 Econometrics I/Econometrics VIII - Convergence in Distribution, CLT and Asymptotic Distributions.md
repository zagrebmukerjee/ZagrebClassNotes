---
aliases:
- "CLT"
- "Central Limit Theorem"
creation date: Sunday, October 30th 2022, 9:44 am
date updated: Sunday, October 30th 2022, 11:50 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Econometrics VIII - Convergence in Distribution, CLT and Asymptotic Distributions]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Convergence in Distribution


Convergence in Distribution is a second type of convergence. Convergence in probability describes, loosely, a density collapsing to a spike over a point. Convergence in distribution describes a density coverging to another density. This will be useful for us to talk about the asymptotic distribution of sample statistics. After all, we know that the sample mean is converging to a spike. But how long will it take to get there? And what will it look like on the way?

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
where $Z \sim \mathcal N(0,1)$. 

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

We will use this to generate a multivariate CLT. We know that $c' \sqrt{n}(\overline Y_n - mu) \to_d N(0, c' \sigma^2 c)$. Then it follows that $\sqrt{n}(c' \overline Y_n - c' mu) \to_d N(0, c' \sigma^2 c)$
