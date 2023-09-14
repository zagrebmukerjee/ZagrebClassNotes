---
aliases:
  - CES Utility
  - CES utility function
creation date: Thursday, September 14th 2023, 1:51 pm
date updated: Thursday, September 14th 2023, 3:04 pm
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

Many old friends are special cases of the CES utility function. I will make the case with the simple form $U(x_1, x_2) = (a x_1 ^\rho + (1 - a)x_2^\rho)^{1/\rho}$ for simplicity, where $\rho = \frac{\sigma-1}{\sigma}$

#### Linear Utility
Let $\sigma \to \infty$ which means $\rho \to 1$; then 
$$U(x) = ax_1 + (1 - a)x)2$$


#### Cobb-Douglas
Let $\sigma \to 1$ which means $\rho \to 0$. 

Take the log and then use L'Hopital's Rule: 

$$\begin{align}
\lim_{\rho \to 0} U(x; \rho) &= \exp \lim_{\rho \to 0} \ln U(x; \rho)\\
&= \exp \lim_{\rho \to 0}  \frac{\ln [ax_1^\rho + (1-a)x_2^\rho]}{\rho}\\
&= \exp \lim_{\rho \to 0}  \frac{\frac{d}{d\rho}\ln [ax_1^\rho + (1-a)x_2^\rho]}{\frac{d}{d\rho}\rho}\\
&=\exp \lim_{\rho \to 0}  \frac{\frac{d}{d\rho}[ax_1^\rho + (1-a)x_2^\rho]}{ax_1^\rho + (1-a)x_2^\rho}\\
&=\exp  \frac{ax_1^0 \ln x_1+ (1-a)x_2^0\ln x_2}{ax_1^0 + (1-a)x_2^0}\\
&= x_1^ax_2^{1-a}\\
\end{align}$$
which is recognizable as the Cobb-Douglas. 

#### Leontief

The most annoying. 
Again take the log and then use L'Hopital's Rule: 

$$\begin{align}
\lim_{\rho \to -\infty} U(x; \rho) &= \exp \lim_{\rho \to  -\infty} \ln U(x; \rho)\\
&= \exp \lim_{\rho \to  -\infty}  \frac{\ln [ax_1^\rho + (1-a)x_2^\rho]}{\rho}\\
&= \exp \lim_{\rho \to  -\infty}  \frac{\frac{d}{d\rho}\ln [ax_1^\rho + (1-a)x_2^\rho]}{\frac{d}{d\rho}\rho}\\
&=\exp \lim_{\rho \to  -\infty}  \frac{\frac{d}{d\rho}[ax_1^\rho + (1-a)x_2^\rho]}{ax_1^\rho + (1-a)x_2^\rho}\\
\end{align}$$
