---
aliases:
creation date: Monday, November 7th 2022, 12:41 pm
date updated: Thursday, November 17th 2022, 1:30 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Estimation IV - Maximum Likelihood Estimation]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 550 Index]]
A more mathematical treatment of [[2001.6 Likelihood Inference]].


## Basics

The MLE method requires picking a <font color=gree>parametric family</font> of distributions, $\mathcal F = \{f_Y(y; \theta):\theta \in \R^k\}$. In other words, same densities up to some parameter(s) $\theta$. For instance, $N(\mu, \sigma^2)$ is a parametric family (with $\theta = [\mu, \sigma]$; members of this family are $N(0,1), N(12.2, 40)$ etc. 

We observe a <font color=gree>sample</font>, $n$ i.i.d $Y_i$s, all drawn from the same $f_Y$. By independence, they have a joint density: 
$$ f_{Y_1, \ldots, Y_n} = \prod_{i=1}^Nf_Y(Y_i; \theta)$$
For any given sample $Y_i$, we can then say there is some unknown joint density from which this sample was drawn. We can call this the Likelihood function: 
$$ \mathcal L(\theta|Y_1 = y_1, \ldots, Y_n = y_n) = \prod_{i=1}^Nf_Y(\theta|Y_i = y_i)$$
For convenience we can call this $\mathcal L(\theta; \underline y)$. Maximizing this likelihood function over all $\theta \in \Theta$ gives us the value $\theta_{MLE}$ that is most likely (by definition; the word is used particularly here) to have generated our data. 

We can maximize the log-likelihood instead, since log is a strictly increasing transformation. 
$$\log \mathcal L(\theta; \underline y)= \sum_{i=1}^N \log f_Y(y_i;\theta)$$

We'll have some FOCs: 
$$0 = \frac{d}{d\theta} \sumn{i} \log f_Y(y_i;\theta)$$

Sometimes we'll be able to solve these FOCs analytically to find a general expression for a maximum likelihood estimator. 

```ad-example
title: Maximum Likelihood Estimation of Linear Regression Model

Suppose I have the linear regression parametric family; that is, $Y_i$ are iid, with 

$$ Y_i \sim N(\alpha + \beta x_i, \sigma^2)$$
where $x_i$ are distributed according to some joint density $g(x_1, \ldots, x_n)$ that's independent of $Y$. Now we want a conditional joint density of $Y_i|X$; then

$$\begin{align}
\mathcal L(y_i|x_i;\theta) &= \prod_{i=1}^n \frac{1}{\sqrt{2\pi\sigma^2}}\exp\left[-\frac{1}{2}\frac{(y_i - (\alpha + \beta x_i))^2}{\sigma^2}\right]\\
\log \mathcal L(y_i|x_i;\theta) &= \sumn{i} \log \frac{1}{\sqrt{2\pi\sigma^2}}\exp\left[-\frac{1}{2}\frac{(y_i - (\alpha + \beta x_i))^2}{\sigma^2}\right]\\
&= \sumn{i} \left[-\frac{1}{2}\frac{(y_i - (\alpha + \beta x_i))^2}{\sigma^2}\right] + 1/2\log 2\pi + \log \sigma\\
&= n/2\log 2\pi + n \log \sigma -\frac{1}{2\sigma^2}\sumn{i}(y_i - (\alpha + \beta x_i))^2\\
&= n/2\log 2\pi + n \log \sigma -\frac{1}{2\sigma^2}\sumn{i}(\alpha + \beta x_i)^2 - 2 y_i (\alpha + \beta x_i) + y_i^2 \\
\end{align}$$
The first order conditions are: 
$$\begin{align}
0 &= \frac{d}{d\alpha} \left[n/2\log 2\pi + n \log \sigma - \frac{1}{2\sigma^2}\sumn{i}(\alpha + \beta x_i)^2 - 2 y_i (\alpha + \beta x_i) + y_i^2 \right]\\
&= -\frac{1}{2\sigma^2}\frac{d}{d\alpha} \left[\sumn{i} \alpha^2 + 2\alpha \beta x_i + \beta^2 x_i^2 - \sumn{i} 2 y_i \alpha - 2 y_i \beta x_i\right]\\
&= -\frac{1}{2\sigma^2}\frac{d}{d\alpha} \left[n\alpha^2 + 2\alpha \sumn{i}\beta x_i- \alpha \sumn{i} 2 y_i\right]\\
\alpha &= \Ybar_n - \beta\Xbar_n\\
0 &= \frac{d}{d\beta} \left[n/2\log 2\pi + n \log \sigma - \frac{1}{2\sigma^2}\sumn{i}(\alpha + \beta x_i)^2 - 2 y_i (\alpha + \beta x_i) + y_i^2 \right]\\
&=- \frac{1}{2\sigma^2}\frac{d}{d\beta} \left[\sumn{i} \alpha^2 + 2\alpha \beta x_i + \beta^2 x_i^2 - \sumn{i} 2 y_i \alpha - 2 y_i \beta x_i\right]\\
&=-\frac{d}{d\beta} \left[2\alpha \beta\sumn{i} x_i + \beta^2\sumn{i} x_i^2 - 2 \beta \sumn{i} y_i x_i\right]\\
&=- 2\alpha \sumn{i} x_i - 2 \beta\sumn{i} x_i^2 + 2\sumn{i} y_i x_i\\
&= \beta\Xbar_n\sumn{i} x_i - \Ybar_n\sumn{i} x_i - \beta\sumn{i} x_i^2 + \sumn{i} y_i x_i\\
&=\beta\Xbar_n^2/n+\Ybar_n\Xbar_n/n - \beta\sumn{i} x_i^2 - \sumn{i} y_i x_i\\
\betahat_{MLE } &= \frac{\sumn{i}[x_i -\Xbar_n][y_i - \Ybar_n]}{\sumn{i} [x_i - \Xbar_n]^2}\\
\end{align}$$
This is also the OLS estimator <font color=#F7B801>why tho?</font>


Also 
$$\begin{align}
0 &= \frac{d}{d\sigma} \left[n/2\log 2\pi + n \log \sigma - \frac{1}{2\sigma^2}\sumn{i}(\alpha + \beta x_i)^2 - 2 y_i (\alpha + \beta x_i) + y_i^2 \right]\\
&= \frac{d}{d\sigma} \left[n \log \sigma - \frac{1}{2}\sigma^{-2}\sumn{i}\hat u_i^2 \right]\\
&= n \sigma\inv + \sigma^{-3} \sumn{i}\hat u_i^2 \\
\hat\sigma^2_{MLE} &= n\inv \sumn{i}\hat u_i^2 
\end{align}$$

This can be shown to be biased towards $0$ by a factor of $(n-2)/n$. 

```



## Estimator Properties

The ML method is pretty broadly applicable to families of parametric models, and allows for analytic or numerical solutions in a number of cases. 

Under certain broad conditions, the MLE has desirable asymptotics: 
1) Consistency
2) Asymp. Normality
3) Asymptotic efficiency - discussed later. 

$$ MLE(g(\theta)) = g(MLE(\theta))$$
Unfortunately, we don't have any understanding of whether ML estimators have good finite sample properties. Also there are several parametric families for which the ML is not so good, and some for which the ML is not defined. 


### Consistency

We can write down a <font color=gree>criterion function</font> to describe the MLE process (and now this is something to minimize)

$$ Q_n(\theta) = -n\inv \sumn{i} \log f(Y_i, \theta)$$
Let $W_i = \log f(Yi, \theta)$; then by the WLLN we have $Q_n(\theta) = -\overline W_n \to_p -EW_n = -E_{\theta_0} \log f(Y, \theta) = Q(\theta)$, if $E_{\theta_0} \log f(Y, \theta)$ is finite. Here $E_{\theta_0}$ means the expectation under the 'true distribution'; ie $f(y, \theta|\theta = \theta_0)$, or $f(y, \theta_0)$. 

Consider $Q(\theta_0) - Q(\theta)$ for any $\theta \in \Theta$:

$$\begin{align}
Q(\theta_0) - Q(\theta) &= -n\inv \sumn{i} \log f(Y_i, \theta_0) + n\inv \sumn{i} \log f(Y_i, \theta)\\
&= -E_{\theta_0}\log f(Y_i, \theta_0) - E_{\theta_0}\log f(Y_i, \theta)\\
&= E_{\theta_0}\log f(Y_i, \theta)/ f(Y_i, \theta_0)\\
&\leq \log E_{\theta_0} f(Y_i, \theta)/ f(Y_i, \theta_0) \text{ by Jensen}\\
&\leq \log \int \left[f(Y_i, \theta)/ f(Y_i, \theta_0)\right] f(y, \theta_0) d \mu y\\
&\leq \log \int f(Y_i, \theta) d \mu y\\
&\leq \log 1\\
&\leq 0
\end{align}$$
[[Jensen's inequality]] applies here because $\log$ is concave. Since it's strictly concave, the inequality is strict wherever $\theta \neq \theta_0$. 

So we can see that maximizing the criterion function, in the limit, is maximizing the true criterion function; and since the true value uniquely maximizes the true criterion function, we are approximating the true value with our MLE (some more technical conditions are needed for this?)

### Normality

Suppose $\theta \in \text{int}(\Theta)$ and $f$ twice continuously differentiable wrt $\theta$. Assume $Y_i$ iid with $f(y, \theta)$. 

Reiterate the log-likelihood, a random function of $\theta$:

$$ \log \mathcal L(\theta, y) = \sumn{i} \log f(y_i, \theta)$$
Let $\hat \theta_n$ be the maximizing $\theta$. As $n \to \infty$, $\hat\theta_n$ is in the interior of $\Theta$ with probability 1 (since it's getting very close to $\theta_0$ per consistency above). So I can reliably say the FOCs for likelihood maximization hold:
$$ 0 =n\inv \sumn{i}\frac{\partial }{\partial \theta}\log f(y_i, \thetahat_n)$$

Sometimes the RHS is called a <font color=gree>score function</font>. 

### Andrews Derivation


Now we can use the [[Mean Value Theorem]] on $f'$ to expand:

$$\begin{align}
\forall i; \;0 &=\frac{\partial }{\partial \theta}\log f(y_i, \thetahat_n)\\
&=\frac{\partial }{\partial \theta}\log f(y_i, \theta_0) + \frac{\partial^2 }{\partial \theta \partial \theta'}\log f(y_i, \tilde \theta)(\thetahat - \theta_0) \\
&= n\inv \sumn{i} \frac{\partial }{\partial \theta}\log f(y_i, \theta_0) + \left[n\inv \sumn{i} \frac{\partial^2 }{\partial \theta \partial \theta'}\log f(y_i, \tilde \theta)\right](\thetahat - \theta_0) 
\end{align}$$

where $\tilde \theta$ is a convex combination of $\thetahat, \theta_0$. Since it is, we can say that $||\tilde \theta - \theta_0|| \leq ||\hat \theta - \theta_0||$. But by WLLN we know that $||\thetahat - \theta_0||\to_p 0$. 

We can rearrange to get a familiar form

$$\begin{align}
 \left[n\inv \sumn{i} \frac{\partial^2 }{\partial \theta \partial \theta'}\log f(y_i, \tilde \theta)\right](\thetahat - \theta_0) &= -n\inv \sumn{i} \frac{\partial }{\partial \theta}\log f(y_i, \theta_0)\\
 (\thetahat - \theta_0) &= -\left[n\inv \sumn{i} \frac{\partial^2 }{\partial \theta \partial \theta'}\log f(y_i, \tilde \theta)\right]\inv n\inv \sumn{i} \frac{\partial }{\partial \theta}\log f(y_i, \theta_0)\\
 \sqrt{n}(\thetahat - \theta_0) &= -\left[n\inv \sumn{i} \frac{\partial^2 }{\partial \theta \partial \theta'}\log f(y_i, \tilde \theta)\right]\inv \sqrt{n}\inv \sumn{i} \frac{\partial }{\partial \theta}\log f(y_i, \theta_0)\\
\end{align}$$
From this point it can be shown using the regularity conditions and the WLLN that  <font color=#F7B801>how?</font>
$$ n\inv \sumn{i} \frac{\partial^2 }{\partial \theta \partial \theta'}\log f(y_i, \tilde \theta) \to_p E_{\theta_0}\log f(y_i, \tilde \theta)$$

### Alternative Derivation

$$ 0 =n\inv \sumn{i}\frac{\partial }{\partial \theta}\log f(y_i, \thetahat_n)$$

Sometimes the RHS is called a <font color=gree>score function</font> $U(\theta)$ or $U_n(\theta)$. The variance $\var(\mathcal L_n'(\theta))$ is called an <font color=gree>information matrix</font> or <font color=gree>Fisher information matrix.</font>

We know that $\int f_\theta(x) dx = 1$; so, differentiating both sides, we can say that $\int f'(\theta)