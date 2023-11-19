---
aliases:
  - CES Utility
  - CES utility function
  - Constant Elasticity of Substitution
  - Cobb-Douglas
creation date: Thursday, September 14th 2023, 1:51 pm
date updated: Monday, October 2nd 2023, 3:03 pm
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

A utility function that has a constant elasticity of substitution across goods. A fairly general example of the form is in terms of a Lebesgue integral over a set of goods $\Omega = \{ \omega\}$, with consumption $c(\omega)$: 

$$U(\{c(\omega)\}) = \left(\int_{\omega \in \Omega} c(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1}$$
Has many nice properties. Most obviously homogeneous of degree $1$: 

$$\begin{align}
U(\{\lambda c(\omega)\}) &= \left(\int_{\omega \in \Omega} (\lambda c(\omega))^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1}\\
&=  \left(\lambda^\frac{\sigma - 1}{\sigma} \int_{\omega \in \Omega} c(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1}\\
&= \lambda \left(\int_{\omega \in \Omega} c(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1}\\
&= \lambda U(\{c(\omega\})\\
\end{align}$$
i.e. preferences are homothetic. 

## Utility Maximization
With income $E$ and prices $p(\omega)$ the Lagrangian is:

$$ \mathcal L = \left(\int_{\omega \in \Omega} c(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1} + \lambda\left( E -  \int_{\omega \in \Omega} c(\omega)p(\omega) d\omega\right)$$

Fix some $\omega, \omega'$. The first order condition for $c(\omega)$ is 

$$\begin{align}
\frac{d\mathcal L}{dc(\omega)} &= \frac{\sigma}{\sigma-1}  \left(\int_{\omega \in \Omega} x(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^{\frac{\sigma}{\sigma-1}-1} \frac{\sigma-1}{\sigma} c(\omega)^{\frac{\sigma - 1}{\sigma} -1} - \lambda p(\omega)\\
\lambda p(\omega)&= \left(\int_{\omega \in \Omega} c(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^{\frac{1}{\sigma-1}}c(\omega)^{-\frac{1}{\sigma}}\\
\frac{p(\omega)}{p(\omega')} &= \frac{c(\omega)^{-\frac{1}{\sigma}}}{c(\omega')^{-\frac{1}{\sigma}}}\\
\frac{c(\omega)}{c(\omega')} &= \left(\frac{p(\omega)}{p(\omega')} \right)^{-\sigma}\\
c(\omega) &= \left(\frac{p(\omega)}{p(\omega')} \right)^{-\sigma} c(\omega')
\end{align}$$


### Marshallian

Fix some $\omega'$. Let $x(\omega')$ be the Marshallian demand for good $\omega'$. From the $\lambda$ FOC we have

$$\begin{align}
E &= \int_{\omega \in \Omega} c(\omega)p(\omega) d\omega \\
&= \int_{\omega \in \Omega} \frac{p(\omega)^{-\sigma}}{p(\omega')^{-\sigma}}  x(\omega')p(\omega) d\omega\\
&= x(\omega')p(\omega')^{\sigma} \int_{\omega \in \Omega} p(\omega)^{1-\sigma}  d\omega\\
x(w') &= \frac{p(\omega')^{-\sigma}}{\int_{\omega \in \Omega} p(\omega)^{1-\sigma}  d\omega}E
\end{align}$$
We can simplify this further by defining the Spence-Dixit-Stiglitz Price Index specific to set $\Omega$, prices $p()$, and $\sigma$:

$$ P \equiv \left( \int_{\omega \in \Omega} p(\omega)^{1-\sigma}\right)^\frac{1}{1-\sigma}$$

Then 

$$x(w') = \frac{p(\omega')^{-\sigma}}{P^{1-\sigma}}E$$
In terms of expenditure: 

$$x(w')= \frac{p(\omega')^{1-\sigma}}{P^{1-\sigma}}E$$

Expenditure share: 
$$x(w')= \frac{p(\omega')^{1-\sigma}}{P^{1-\sigma}}$$ 
### Indirect Utility

Plug the Marshallians into the utility function 
$$\begin{align}
V(\{p(\omega)\}, E) &= U(\{x(\omega)\}) \\
&= \left(\int_{\omega \in \Omega} x(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1}\\
&= \left(\int_{\omega \in \Omega} \left(\frac{p(\omega)^{-\sigma}}{P^{1-\sigma}}E \right)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1}\\
&= \frac{E}{P^{1-\sigma}}  \left(\int_{\omega \in \Omega} (p(\omega)^{-\sigma})^\frac{\sigma-1}{\sigma}d \omega\right)^\frac{\sigma}{\sigma-1}\\
\end{align}$$

somehow becomes $E/P$ <font color=#F7B801>why</font>

## Cost Minimization

Problem is dual to above: 
$$\begin{align}
\mathcal L &= \int_{\Omega} p(\omega)c(\omega) - \lambda(\bar u - U(\{c(\omega)\})\\ 
\frac{d\mathcal L}{dc(\omega)} &= p(\omega') - \lambda \frac{dU}{dc(\omega')}  \\
p(\omega') &= \lambda \left( \int_\Omega c(\omega)^\frac{\sigma-1}{\sigma}\right)^\frac{1}{\sigma-1}c(\omega')^{-1/\sigma}\\
\frac{p(\omega)}{p(\omega')} &= \frac{ c(\omega')^{1/\sigma}}{ c(\omega)^{1/\sigma}}\\
c(\omega) &= c(\omega') \left(\frac{p(\omega')}{p(\omega)}\right)^\sigma
\end{align}$$

### Hicksian

Plug into the other FOC:

$$\begin{align}
\bar U &= U(\{c(\omega)\})\\
&= \left(\int_{\omega \in \Omega} c(\omega)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1} \\
&= \left(\int_{\omega \in \Omega} \left( h(\omega') \left(\frac{p(\omega')}{p(\omega)}\right)^\sigma\right)^\frac{\sigma-1}{\sigma} d \omega\right)^\frac{\sigma}{\sigma-1} \\
&= h(\omega')p(\omega')^{\sigma}\left( \int p(\omega)^{1-\sigma} d\omega\right)^\frac{\sigma}{\sigma-1} \\
&= h(\omega')p(\omega')^{\sigma}\left( P^\frac{1}{1-\sigma}\right)^\frac{\sigma}{\sigma-1} \\
&= h(\omega')p(\omega')^{\sigma}P^{-\omega} \\
h(\omega'; \{p(\omega)\}, \bar U) &= \frac{p(\omega')^{-\sigma}}{P^{-\sigma}} \bar U
\end{align}$$

Can then plug back in to the FOC:
$$\begin{align}
p(\omega') &= \lambda \frac{dU}{dc(\omega')}\\
\frac{dU}{dc(\omega')}\bigg|_{c(\omega) = h}&= \left( \int_\Omega h(\omega)^\frac{\sigma-1}{\sigma}d\omega\right)^\frac{1}{\sigma-1}h(\omega')^{-1/\sigma}\\
&= \left( \int_\Omega\left(  \frac{p(\omega)^{-\sigma}}{P^{-\sigma}} \bar Ud\omega\right)^\frac{\sigma-1}{\sigma}\right)^\frac{1}{\sigma-1}\left( \frac{p(\omega')^{-\sigma}}{P^{-\sigma}} \bar U \right)^{-1/\sigma}\\
&= \bar U^{1/\sigma}\left( \frac{p(\omega')}{P} \right)\bar U^{-1/\sigma}\\
\end{align}$$
As an aside:
$$
\begin{align}\lambda &= p(\omega')\bigg/ \frac{dU}{dc(\omega')}\\
&= p(\omega')\big/ (p(\omega')/P)\\
&= P
\end{align}$$


## Constancy of Elasticity

The [[Micro Theory IIa - Elasticity|Elasticity]] of substitution - in expenditure terms - is defined as 
$$\begin{align}
\varepsilon_{\omega\omega'} &= \frac{d \ln \left[ p(\omega) x(\omega)/p(\omega') x(\omega')\right] }{d\ln \left[p(\omega)/p (\omega') \right]}\\
\end{align}$$
ie. if the price of $\omega$ rises $1\%$ more than that of $\omega'$, how will the expenditures shift?
Use the first order conditions to find 
$$ \ln \left[p(\omega)/p (\omega') \right] = -\frac{1}{\sigma}\ln \left[x(\omega)/x(\omega') \right] $$
Then
$$\begin{align}
\varepsilon_{\omega\omega'} &= \frac{d \ln \left[ p(\omega)/p(\omega')] + \ln[ x(\omega)/x(\omega')\right] }{d-\frac{1}{\sigma}\ln \ln \left[x(\omega)/x(\omega') \right]}\\
&= \frac{d \ln \left[ p(\omega)/p(\omega')] + \ln[ x(\omega)/x(\omega')\right] }{d-\frac{1}{\sigma}\ln \ln \left[x(\omega)/x(\omega') \right]}\\
&= \frac{d -\frac{1}{\sigma}\ln \left[x(\omega)/x(\omega') \right]}{d-\frac{1}{\sigma}\ln  \left[x(\omega)/x(\omega') \right]} - \frac{d\ln[ x(\omega)/x(\omega')]}{d\frac{1}{\sigma}\ln  \left[x(\omega)/x(\omega') \right]}\\
&= 1 - \sigma
\end{align}$$
as desired.

## Limits of CES

Many old friends are special cases of the CES utility function. I will make the case with the form $U(x_1, x_2) = (a x_1 ^\rho + (1 - a)x_2^\rho)^{1/\rho}$ for simplicity, where $\rho = \frac{\sigma-1}{\sigma}$

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


## Two-Stage Property

Shared by all homothetic utility functions. I know that $\lambda = P$ the price index. So 
🚧


## Cobb-Douglas: Expansion

Suppose Cobb-Douglas production. The firm wants to maximize profit

$$\pi = \max_x p \prod x_i^{\alpha_i} - \sum_i w_i x_i$$
May be salutary to approach this from the direction of cost minimization. Minimize the unit cost: 

$$ c_1 = \min_{x} \sum_i w_i x_i \text{ subject to } $$