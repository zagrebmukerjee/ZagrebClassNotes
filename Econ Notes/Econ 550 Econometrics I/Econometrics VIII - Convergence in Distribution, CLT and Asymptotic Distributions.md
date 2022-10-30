---
aliases:
- "CLT"
- "Central Limit Theorem"
creation date: Sunday, October 30th 2022, 9:44 am
date updated: Sunday, October 30th 2022, 9:47 am

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

### Properties 
Suppose $Y_n \to_d Y$ and $Z_n \to_p z$. Then:
1) $Y_n + Z_n \to_d Y + z$
2) $Y_nZ_n \to_d zY$
3) $Y_n/Z_n \to_d Y/z$ where $z \neq 0$. 

For 1):  We want to show that $\lim_{n\to\infty} P(Y_n + Z_n \leq a) = P(Y + z \leq a)$. $P(Y_n + Z_n \leq a) = P(Y_n + (Z_n -z) \leq a -z )$. But as $n \to \infty$, $Z_n - z \to 0$;  so  $P(Y_n + (Z_n - z) \leq a-z) \to P(Y_n \leq a -z) \to P(Y \leq a -z)$. 

For 2) consider the asymptotic distribution of $Y_n Z_n - Y_n z = Y_n (Z
