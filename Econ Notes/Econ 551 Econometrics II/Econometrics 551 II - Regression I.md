---
aliases:
creation date: Friday, February 17th 2023, 11:12 am
date updated: Friday, February 17th 2023, 11:27 am

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




### Variance

Define $\sigma^2 = \var (e)$. Finite variance of $Y$ means finite variance of $e$. Alternatively, let $\sigma^2 = \var(Y|X)$; then 
$$ \var(Y|X) = E[(Y - E[Y|X))^2|X] = E[(m(X) + e - m(X))^2|X] = E[e^2|X] = E[e^2|X] - E[e|X]^2= \var(e|X)$$

