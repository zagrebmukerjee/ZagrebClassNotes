---
aliases:
creation date: Wednesday, September 21st 2022, 3:13 pm
date updated: Tuesday, October 4th 2022, 11:57 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
---

# [[Econometrics IV - Moments]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

[[Econ 550 Index]]

## Expectations

From [[2002.1 Probability|Gov 2002]]:
![[2002.1 Probability#Expected Value]]

We can take this back to our original $\Omega$:
$X$ is a random vector on $\Omega, \mathcal F, P$. $E g(X)$ is finite. Then


$$ Eg(X) = \int g(X) dP = \int g X(\omega)d P(\omega)$$


#### Theorem
- $E(g(x)) = \int g d P_X$ where $P_X$ is the distribution of $X$;
- $Eg(X) = \int g f_X d\mu$ IF $P_X << \mu$ and $\mu$ is $\sigma$-finite. 

Proof: Start with nonnegative simple functions. Let $\{A_k\}$ be some disjoint sets in $\mathcal B(\Omega_X)$. Define a simple function $g(x) = \sum_{k=1}^K c_k 1_{A_k}(x)$. 

We can write this in terms of the pre-image of $A$ in $\Omega$. 
$$\begin{align}
g(X(\omega)) &= \sum_{k=1}^K c_k 1_{A_k}(X(\omega)) \\
&= \sum c_k1_{X\inv(A_k)}(\omega)\\
\int g(X)d P &= \sum_{k=1}^K c_k P(X\inv(A_k)) \\
&= \sum_{k=1}^K c_k P(X \in A_k) \\
&= \sum_{k=1}^K c_k P_X(A_k) \\
&= \int g d P_X
\end{align}$$
Extend to general non-negative functions: let $s_n(x)$ converge to $g(x)$ from below almost everywhere. Then use the MCT:

$$\begin{align}
\int gd P_X &= \lim_{n \to \infty} \int s_ndP_X\\
&= \lim_{n \to \infty} \int s_n(X) dP\\
&= \int g(X) dP
\end{align}$$

We can extend this to all functions in the same way as with [[Econometrics IIIa - Linearity of Lebesgue Integral]]

```ad-example
title: Example: Expectations of Common Distributions


#### Uniform Distribution
$$\begin{align}
X &\sim U(a,b)\\
EX &= \int x f_X(x)dx \\
&= 1/(b-a)\int_a^b x dx \\
&= (x^2/2)/(b-a) \big|^b_a \\
&= \frac{b^2-a^2}{2(b-a)}\\
&= a+b/2
\end{align}$$

#### Exponential Distribution
$$\begin{align}
f_X &= \begin{cases} 
\theta\exp(-\theta x) &\text{ if } x > 0 \\
0 &\text{ otherwise}\\
\end{cases}\\
EX &= \int_0^{\infty} x\theta\exp(-\theta x) dx\\
\int u dv &= uv|_0^\infty - \int v du \\
\int_0^{\infty} [x][\theta\exp(-\theta x) dx] &= -x\exp(-\theta x)|_0^\infty + \int_0^\infty \exp(-\theta x) dx \\
&= -\frac{1}{\theta e^{\theta x}}\bigg|_{0}^\infty\\
&= 1/\theta\\
\end{align}$$




```

The expectation can also be interpreted as the 'fair price' of a gamble: if $X$ is $1$ if a fair coin comes up heads, $0$ otherwise, then the fair price of this game is $1/2$. 



## Moments

The expectation, or mean, is the first moment of a random variable - a measure of centrality. Generally the $r\th$ moment is $E(X^r)$. $E(X^r)$ is only well defined if $E|X^r|$ is. For $r>1$ we might prefer to talk about 'moments around the mean'. For example, $E(X^r)$ will change as $E(X)$ changes. So we can instead compute $E[X - E(X)]^r$, the $r\th$ moment about the mean. 

The first few moments have special names/properties: 
1) $E(X)$ is the mean. 
2) $E[X - E(X)]^3$ is the variance, a measure of dispersion.
3) $E[X - E(X)]^3$ is skewness. 
4) $E[X - E(X)]^4$ is kurtosis. 

Moments 3 and 4 take advantage of the sign properties of the cubic and quartic. It's more intuitive to normalize them to the variance, so we have $E\left( \dfrac{x - E(X)}{\sigma_X}\right)^r$, the moments of the $z$-scores. So then we can compare to eg. the kurtosis of the standard normal (3). 


### Moment Generating Function

The MGF makes it easy to find moments. It's a function such that $M'(t)|_{t=0} = E(X)$, $M''(t)|_{t=0} = E(X^2)$ and so on. 

Define the MGF $M(t) = E[e^{tX}]$. 

This function is unique: two functions have the same MGF iff they have the same distribution. Not all variables have an MGF; all moments must exist for the MGF to exist, i.e. $E|X^r| < \infty$.


#### Example: $\mathcal N(0,1)$
Suppose $Z$ is a standard normal. Then $f_Z(x) = (1/\sqrt{2\pi})\exp[-x^2/2]$. The MGF is $E\exp\left[(t/\sqrt{2\pi})\exp[-x^2/2]\right]$. The first deriviative:
$$\begin{align}
M(t) &= Ee^{tX} \\
&= \int_{-\infty}^\infty \exp({tx})f_X(x)dx\\
&= \int_{-\infty}^\infty \exp({tx})\left( (1/\sqrt{2\pi})\exp[-x^2/2]\right)dx\\
&= (1/\sqrt{2\pi}) \int_{-\infty}^\infty \exp\left[-(x^2 - 2tx)/2\right]dx\\
&= (1/\sqrt{2\pi}) \int_{-\infty}^\infty \exp\left[-(x^2 - 2tx + t^2 - t^2)/2\right]dx\\
&= (1/\sqrt{2\pi}) \int_{-\infty}^\infty \exp\left(-t^2/2 \right) \exp\left[-(x-t)^2/2\right]dx\\
&= \exp\left(-t^2/2 \right) (1/\sqrt{2\pi}) \int_{-\infty}^\infty \exp\left[-(x-t)^2/2\right]dx\\
\end{align}$$

This last integral is simply the PDF of the normal distribution once more, with mean shifted to $x-t$; so we know it integrates to $1$, and the MGF is then $e^{-t^2/2}$. 


### Non-Finite Moments

In general we don't always have finite moments. We can say a few things about infinite moments:
- If $E|X^r| < \infty$ then $s < r \to E|X^s| < \infty$
- If $E|X^r| = \infty$ then $s > r \to E|X^s| = \infty$
- straightforward to show by decomposing $E|X^r| \iff E|X^r| * 1_{|X| \geq 1} = 0 \iff E|X^{r+1}| = 0$


### Characteristic Function

When the moments are not finite we have instead the characteristic function. This is 

$$ \text{cf}(X) = E|\exp[itX]|$$
Define a complex random variable as $(X_1, X_2)$ or $X_1 + iX_2$. The expectation is simply $(EX_1, EX_2)$. We can transform the cf: 
$$\begin{align}
\exp[itX]| &= | \cos(tX) + i \sin (tX)| \\
&= |\sqrt{\cos^2(tX) - \sin^2 (tX) + 2i\cos(tX)\sin(tX)}|\\
&= |\sqrt{(\cos(tX) + i\sin(tX))(\cos(tX) - i\sin(tX) )}|\\
&= |\sqrt{\cos^2(tX) + \sin^2(tX)}|\\
&= 1
\end{align}$$

So the characteristic function is well defined for any $X$. You can differentiate it $r$ times to get the $r\th$ moment. 
