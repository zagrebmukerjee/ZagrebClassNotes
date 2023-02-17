---
aliases:
creation date: Friday, February 17th 2023, 11:12 am
date updated: Friday, February 17th 2023, 12:47 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Econometrics 551 II - Regression I]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


Recall the definition of conditional expectation function from [[Econometrics 551 I - Conditional Expectation]] as an orthogonal projection: given $M$ the set of square integrable functions (functions with $\int |m(x)|^2 dx < \infty$), the CEF is 

$$ \min_{m \in M} E[(Y - m(X))^2]$$
or equivalently, $m$ such that 
$$E[(Y - m(X))g(X)] = 0$$ 
for any square-integrable $g(X)$. 

## Regression

### CEF and Error

Let $e = Y - m(X)$. Then $Y = m(X) + e$. $m$ is a '<font color=gree>mean regression function</font>', and $e$ is '<font color=gree>regression error</font>'. This is all by construction, having created $m$ by projecting $X$ onto $Y$. No structural interpretations, no causality yet. 

Alternatively, consider some function $Y = m(X) + e$. 
There are 3 equivalences: 
1) $E(e|X) = 0$ means that $m(X)$ is the conditional expectation function: We know $E(Y|X) = E(m(X) + e|X) = m(X)$
2) $E[Y|X] = m(X)$ means that $E[e|X] = 0$: $E(Y|X) = E(m(X) + e|X) = m(X) + E[e|X] = E[Y|X] + E[e|X]$. 
3) $E[eg(X)] = 0$ for all $g \in M$ means that $m(X)$ is the CEF: $E[(Y - m(X))g(X)]$ $=E[(m(X) - m(X))g(X)] +E[eg(X)]$ $=0$. 

LIE tells us that if $E[e|X] = 0$, then $E[e] = E[E[e|X]] = 0$. 

If we have $Y = m(X) + e$ and $E[e|X] = 0$, with $X$ a random vector, then we can differentiate $m$ to get '<font color=gree>partial effects</font>', $[dm/dX_1\, dm/dX_2]$ etc. 
We can also find an '<font color=gree>average regression derivative</font>,' $E[\nabla m(X)]$ (ie averaging over prob-weighted values of $X$). 




### ANOVA Theorem

Define $\sigma^2 = \var (e)$. Finite variance of $Y$ means finite variance of $e$. Let $\sigma^2(X) = \var(Y|X)$; then 
$$ \var(Y|X) = E[(Y - E[Y|X))^2|X] = E[(m(X) + e - m(X))^2|X] = E[e^2|X] = E[e^2|X] - E[e|X]^2= \var(e|X)$$

The LIE tells us that $\var[E] = E[e^2] = E[E[e^2|X]] = E[\sigma^2(X)]$. 


#### Theorem Statement

$$\var (Y) = \var(E[Y|X]) + E[\var(Y|X)]$$
or 
$$\var (Y) = \var(E[Y|X]) + \sigma^2$$
The first term: unconditional variance in the conditional mean. How much does $E[Y|X]$ vary given the different values $x$ takes on? A measure of across-group variance. Also can think of this as 'explained variance'.

The second term: average conditional variance. Given each $x \in \text{supp} (X)$, what's $\var(Y|X)$? Can think of this as average within-group variance.

```ad-example

Suppose I want to understand the variance in NAFTA wages. I can think of this coming from two differences: 
1) The average wage in the US, Mexico, and Canada vary from each other; and 
2) The wages within the US, Mexico and Canada vary from the country-specific means. 

So, if I just used country to predict wages, my regression would explain the variance to the degree that across-country variance is a big factor relative to within-country. 

This holds for any covariate - the categories don't need special meaning.

```

#### Proof

$$\begin{align}
\var(Y) &= E[(Y - EY)^2]\\ 
&= E\left[((Y - E[Y|X]) + (E[Y|X] - EY))^2\right]\\
&= E\left[(Y - E[Y|X])^2] + E[(E[Y|X] - EY)^2\right] + 2E[(Y - E[Y|X])(E[Y|X]-EY)] \\
\end{align}$$
For the last term, $E[(Y - E[Y|X])(E[Y|X]-Y)]$, that first part is $Y - mX$, and we can interpret $E[Y|X] - Y$ as $g(X)$; so by the orthogonal projection property, this is $0$. 

For the first term,
$$\begin{align}
E[(Y - E[Y|X])^2] &= E[(E[Y|X] + e - E[Y|X])^2]\\
&= E[e^2]\\
&= \sigma^2
\end{align}$$
For the second term: 
$$\begin{align}
EY &= E[E[Y|X]] \\
E[(E[Y|X] - EY)^2] &= E[(E[Y|X] - E[E[Y|X]])^2] \\
&= \var(E[Y|X])
\end{align}$$


## Parametrics

We'll often say that $m$ is known up to a finite dimensional vector, $m^*(x) \in \{ m(x, \theta): \theta  \in \Theta\}$, with $m()$ known tot he analyst. This is a <font color=gree>parametric</font> approach - $\theta$ are the parameters, and $m$ is a <font color=gree>parametric family</font> of models. 

Linear regression is a particular case of this, where $m$ is linear. 

First assume $\theta_0$ is the true value of $\theta$. Then $m(X, \theta_0) = E(Y|X)$. 
Since for all $m$, $E(Y - m(X, \theta_0)^2 \leq E(Y - mX)^2$ - by orthogonality - we can say that $E(Y - m(X, \theta_0)^2 \leq E(Y - m(X, \theta))^2$ for all $\theta \in \Theta$. 

Interpret $m(X, \theta_0)$ as the best approximation to the CEF in that family - so, for instance, the linear $m$ is the best linear predictor of the CEF. 

### Theorem:

Let $Y\in \R$, $X \in \R^k$ such that $EY < \infty$ and $E[m(X,\theta)] < \infty$. Then::

$$ \arg \min_{\theta \in \Theta} E[(Y - m(X, \theta))^2] = \arg \min E[(E[Y|X] - m(X, \theta))^2]$$

The best predictor of the CEF in that family of models is the best predictor of $Y$ in that family. 

#### Proof:

$$\begin{align}
E[(Y - m(X, \theta))^2] &= E(Y - E(Y|X) + E(Y|X) - m(X, \theta))^2\\
&= E[(Y - E(Y|X))^2 + (E[Y|X] - m(X,\theta))^2 + 2 \ldots ]
\end{align}$$

The last term can be killed with the $E[(Y - E(Y|X))g(X)] = 0$ trick again. 

Then what we have left is a constant wrt $\theta$, $E(Y - E[Y|X])^2$, and the part that can actually be minimized. So the minimizers (not the minima!) will be the same. 

## Linear Regression 

Model: Let $Y \in \R$, $X \in \R^k$, $\beta \in \R^k$. $X_0 = 1$; $E[X'X]$ has full rank. Assume $EY^2 < \infty$. 

$$ Y = X'\beta + e$$
This is once again a pure statistical idea: best linear approx to a CEF. 

The following are equivalent: 



