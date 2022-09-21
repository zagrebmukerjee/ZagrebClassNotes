---
aliases:
creation date: Wednesday, September 21st 2022, 3:13 pm
date updated: Wednesday, September 21st 2022, 3:52 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
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
