---
aliases:
  - CES Utility
  - CES utility function
creation date: Thursday, September 14th 2023, 1:51 pm
date updated: Sunday, September 17th 2023, 4:07 pm
notetype: Math Class Note
cssclasses:
  - math-class-note
tags:
  - "#types/classes"
  - "#status/🚧"
---

# [[Constant Elasticity of Substitution Utility Function]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Micro Theory IIa - Elasticity]]
## Intro

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

### UMP

$$ \mathcal L = \left(\int_{\omega \in \Omega} x(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1} - \lambda \int_{\omega \in \Omega} c(\omega)p(\omega) d\omega$$

Fix some $\omega$. The first order condition for $x(\omega)$ is 

$$\begin{align}
\frac{d\mathcal L}{dx(\omega)} &= \frac{\sigma}{\sigma-1}  \left(\int_{\omega \in \Omega} x(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^{\frac{\sigma}{\sigma-1}-1} \frac{\sigma-1}{\sigma} x(\omega)^{\frac{\sigma - 1}{\sigma} -1} - \lambda p(\omega)\\
\lambda p(\omega)&= \left(\int_{\omega \in \Omega} x(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^{\frac{1}{\sigma-1}}\frac{\sigma-1}{\sigma} x(\omega)^{\frac{- 1}{\sigma}}
\end{align}$$
## Constancy of Elasticity

The [[Micro Theory IIa - Elasticity|Elasticity]] of substitution - in expenditure terms - is defined as 
$$\begin{align}
\varepsilon_{\omega\omega'} &= \frac{d \ln \left[ p(\omega) c(\omega)/p(\omega') c(\omega')\right] }{d\ln \left[p(\omega)/p (\omega') \right]}\\
\end{align}$$
## Limits of CES

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

The most annoying. Let $\sigma \to 0$ which means $\rho \to - \infty$.
Again take the log and then use L'Hopital's Rule: 

$$\begin{align}
\lim_{\rho \to -\infty} U(x; \rho) &= \exp \lim_{\rho \to  -\infty} \ln U(x; \rho)\\
&= \exp \lim_{\rho \to  -\infty}  \frac{\ln [ax_1^\rho + (1-a)x_2^\rho]}{\rho}\\
&= \exp \lim_{\rho \to  -\infty}  \frac{\frac{d}{d\rho}\ln [ax_1^\rho + (1-a)x_2^\rho]}{\frac{d}{d\rho}\rho}\\
&=\exp \lim_{\rho \to  -\infty}  \frac{\frac{d}{d\rho}[ax_1^\rho + (1-a)x_2^\rho]}{ax_1^\rho + (1-a)x_2^\rho}\\
&=\exp \lim_{\rho \to  -\infty}  \frac{[ax_1^\rho \ln x_1 + (1-a)x_2^\rho \ln x_2}{ax_1^\rho + (1-a)x_2^\rho}\\
\end{align}$$
Now define $m$ as $\min \{x_1, x_2\}$. Let $y_1, y_2$ = $x_1/m, x_2/m$. Then 

$$\begin{align}
\lim_{\rho \to -\infty} U(x; \rho) &= \exp \lim_{\rho \to  -\infty}  \frac{[ay_1^\rho \ln x_1 + (1-a)y_2^\rho \ln x_2}{ay_1^\rho + (1-a)y_2^\rho}\\
\end{align}$$
Suppose WLOG $x_1 < x_2$; then $y_2 > 1$ and so $y_2^{\rho}$ goes to $0$; but $y_1 =y_1^\rho = 1$. So what's left is

$$\lim_{\rho \to -\infty} U(x; \rho) = \exp \lim_{\rho \to  -\infty}  \ln x_1 = x_1$$
Since $x_1$ was chosen as the minimum: 

$$ \lim_{\rho \to -\infty} U(x; \rho) = \min \{x_1, x_2\}$$