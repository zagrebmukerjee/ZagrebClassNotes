---
aliases: 
tags: 
creation date: Friday, November 18th 2022, 2:12 pm
date updated: Friday, November 18th 2022, 2:13 pm
---

---
aliases:
creation date: 2022-11-18 14:13
date updated: 2022-11-18 14:13

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Estimation IVa - Asymptotic Normality of Score Function]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

TODO: fill in how this goes to MLE
### Score Function-Based Proof of Asymptotic Normality


$$ 0 =n\inv \sumn{i}\frac{\partial }{\partial \theta}\log f(y_i, \thetahat_n)$$

Sometimes the RHS is called a <font color=gree>score function</font> $U(\theta)$ or $U_n$. The MLE is the solution to $U(\theta) = 0$. 

First, start with the identity 

$$\begin{align}
\int f(y, \theta) dy &= 1\\
\int \frac{\partial}{\partial \theta} f(y, \theta) dy &= 0\\
\int \frac{\partial^2}{\partial \theta \partial \theta'} f(y, \theta) dy &= 0\\
\end{align}$$

now, differentiate the score: 
$$\begin{align}
U(\theta) &= \frac{\partial }{\partial \theta}\log f(y_i, \thetahat_n)\\
&= \frac{f(y_i, \thetahat_n)'}{f(y_i, \thetahat_n)}\\
U'(\theta) &=\frac{\partial^2 }{\partial \theta\partial\theta'}\log f(y_i, \thetahat_n)\\
&=\frac{\partial }{\partial \theta}f(y_i, \thetahat_n)'(f(y_i, \thetahat_n)\inv)\\
&=\frac{f''(y_i, \thetahat_n)}{f(y_i, \thetahat_n)}- \frac{f'(y_i, \thetahat_n)^2}{f(y_i, \thetahat_n)^2} \\
\end{align}$$

Then: 
$$\begin{align}
E(U(\theta)) &= \int f(y, \theta) U(\theta)dy\\
&= \int f(y, \theta) \frac{f(y_i, \thetahat_n)'}{f(y_i, \thetahat_n)} dy\\
E(U(\theta)) &= \int f'(y, \theta)dy\\
&= 0
\end{align}$$
and 
$$\begin{align}
E\left(\frac{\partial^2}{\partial \theta \partial \theta'} f(y, \theta) dy)\right) &= \int f(y, \theta) \frac{\partial^2}{\partial \theta \partial \theta'} f(y, \theta) dy\\
&= \int f(y, \theta) \frac{f''(y_i, \theta)}{f(y_i, \theta)}- \frac{f'(y_i, \theta)^2}{f(y_i, \theta)^2} dy\\
&= \int f''(y_i, \theta)- \frac{f'(y_i, \theta)^2}{f(y_i, \theta)} dy\\
&= \int f''(y_i, \theta) dy- \int \frac{f'(y_i, \theta)}{f(y_i, \theta)} dy\\
&= - \int f(y_i, \theta) \frac{f'(y_i, \theta)^2}{f(y_i, \theta)^2} dy\\
&= - E(U(\theta)^2)\\
&= - \var(U(\theta))\\
\end{align}$$

This last term is also called the <font color=gree>Fisher Information Matrix</font>.

Note that $I_n(\theta) = nI_1(\theta))$ <font color=#F7B801>fill in why</font> #status/section/🚧 
