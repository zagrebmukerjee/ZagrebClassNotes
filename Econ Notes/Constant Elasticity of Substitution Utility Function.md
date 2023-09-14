---
aliases:
  - CES Utility
  - CES utility function
creation date: Thursday, September 14th 2023, 1:51 pm
date updated: Thursday, September 14th 2023, 1:57 pm
notetype: Math Class Note
cssclasses:
  - math-class-note
tags:
  - "#types/classes"
  - "#status/🚧"
---

# [[Constant Elasticity of Substitution Utility Function]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

###

A utility function that has a constant elasticity of substitution across goods. One example of the form is in terms of a Lebesgue integral over a set of goods $\Omega = \{ \omega\}$, with consumption $x(\omega)$: 

$$U(\{x(\omega)\}) = \left(\int_{\omega \in \Omega} x(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1}$$
Has many nice properties. Most obviously homogeneous of degree $1$: 

$$\begin{align}
U(\{\lambda x(\omega)\}) &= \left(\int_{\omega \in \Omega} (\lambda x(\omega))^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1}\\
&=  \left(\lambda^\frac{\sigma - 1}{\sigma} \int_{\omega \in \Omega} x(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1}\\
&= \lambda \left(\int_{\omega \in \Omega} x(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1}\\
&= \lambda U(\{x(\omega\})\\
\end{align}$$
i.e. preferences are homothetic. 


### Limits of CES

Many old friends are special cases of the CES utility function. 

As $\sigma \to \infty$ we get linear utility function
$$\begin{align}
 \lim_{\sigma \to \infty} \left(\int_{\omega \in \Omega} x(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1} &=  \int_{\omega \in \Omega} x(\omega) d \omega
\end{align}$$
