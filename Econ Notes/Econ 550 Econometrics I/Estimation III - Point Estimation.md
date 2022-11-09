---
aliases:
creation date: Monday, November 7th 2022, 12:48 pm
date updated: Wednesday, November 9th 2022, 11:40 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Estimation III - Point Estimation]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 550 Index]]

We're now interested in point estimation - the specific values of $\theta$. We say that $\hat\theta_n$ is an <font color=gree>unbiased</font> estimator of $\theta$ if $E_\theta\hat\theta_n = \theta$ for all $\theta \in \Theta$. where $\Theta$ is the parameter space. When it's not unbiased, the bias is $E_\theta \hat\theta_n - \theta$. Unbiasedness is a desirable criterion - not the only one, since given two equally (un)biased estimators one prefers the less biased. 

## Unbiased Minimum Variance Estimator

A (lexicographic) preference across estimators can be expressed with the UMVU criterion: an estimator $\hat\theta^*$ is UMVU if 
1) $E_\theta\hat\theta^* = \theta$ for all $\theta \in \Theta$, and 
2) $\var_\theta(\hat\theta^*) \leq \var_\theta(\hat\theta)$ for any unbiased $\hat \theta$ of $\theta$ for all $\theta \in \Theta$. 

Examples that can be shown to be UMVU:
- For i.i.d. random variables $X_i \sim N(\mu, \sigma^2)$, the estimator $\hat\mu = \Xbar_n$, and $\hat\sigma^2 = S^2_{Xn}$. 
- For i.i.d. $X_i \sim \text{Bern}(\pi)$, the estimator $\hat\pi = \Xbar_n$ 
- For i.i.d. $Y_i = X_i \beta + U_i$ with $U_i$ i.i.d $N(0,\sigma^2)$, the OLS estimator $\betahat$ and the variance estimator $\hat U = (n-2)\inv \sumn{i}\hat U_i^2$, the sum of squared residuals

This is a limiting criterion. We might have an estimator that's not very biased but much lower variance than our UMVU. The requirement that this work for all $\theta$ can be unnecessarily restrictive. And sometimes it si hard to find a UMVU. 


## Mean Squared Error

We can have a different criterion, to sort estimators by errors: 
- $\text{Bias}(\thetahat_n, \theta) = E_\theta(\thetahat_n - \theta$)
- $MSE(\hat \theta_n, \theta) = E_\theta(\hat \theta_n - \theta)^2$.

The MSE can be decomposed in a substantively interesting way: 
$$\begin{align}
MSE(\thetahat_n ,\theta) &= E_\theta(\thetahat_n - \theta)^2 \\
MSE(\thetahat_n ,\theta) &= E_\theta(\thetahat_n -E_\theta\thetahat_n + E_\theta\thetahat_n- \theta)^2 \\
MSE(\thetahat_n ,\theta) &= E_\theta\left[(\thetahat_n -E_\theta\thetahat_n) + (E_\theta\thetahat_n- \theta)\right]^2 \\
MSE(\thetahat_n ,\theta) &= E_\theta\left[(\thetahat_n -E_\theta\thetahat_n)^2 + (E_\theta\thetahat_n- \theta)^2 + 2 (E_\theta\thetahat_n- \theta)(\thetahat_n -E_\theta\thetahat_n)\right] \\
&= E_\theta(\thetahat_n -E_\theta\thetahat_n)^2 + 2 (E_\theta\thetahat_nE_\theta\thetahat_n - E_\theta\thetahat_n\theta - [E_\theta\thetahat_n]^2 + \theta E_\theta\thetahat_n) + E_\theta(\thetahat_n -\theta)]^2 \\
&= E_\theta(\thetahat_n -E_\theta\thetahat_n)^2 + E_\theta(\thetahat_n -\theta)^2 \\
&= [\text{Bias}(\thetahat_n, \theta)]^2 + \var_\theta(\thetahat_n)\\
\end{align}$$

Recall here that $\thetahat_n$ is some function of $\theta$ and other things: so e.g. $E_theta \thetahat_n$ is 