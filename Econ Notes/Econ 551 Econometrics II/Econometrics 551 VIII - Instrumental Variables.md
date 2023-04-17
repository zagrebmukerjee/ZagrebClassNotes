---
aliases:
creation date: Monday, April 17th 2023, 5:02 pm
date updated: Monday, April 17th 2023, 6:32 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#types/classes/stats'
- '#status/🚧'
---

# [[Econometrics 551 VIII - Instrumental Variables]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## Motivation

Instrumental variables are a very popular way to deal with endogeneity - when I think that my regressors are correlated with the (true) error term.

### Endogeneity: Wages and Schooling

Consider a common problem - that of omitted ability bias in determining the effect of schooling on wages. 

$$ Y = \ln w $$
$$ w = p_H \exp[\beta_1 S] \exp[\gamma A] \exp u $$
$$ Y = \ln p_H + \beta_1 S + \gamma A + u$$

Here $w$ is income, $p_H$ is price of human capital, $S$ is schooling, $A$ is ability, and $E[Su] = E[Au] = 0$. 

```ad-note
title: Aside

"Economists doing semi-structural work will reverse engineer a model to correspond (in linearity) to the regression they're going to run." - Ed Vytlacil
```

I can write this also as $Y_i = \beta_0 + \beta_1 S_i + e_i$ where $e = (u - Eu) + \gamma(A - EA)$ - note I've separated $u$ and $\gamma A$ into average parts that will be in $\beta_0$ and individual variation which will be in my error term. But I have a problem. Suppose $S$ is independent of $u$.  

$$\begin{align}
E[eS] &= E[((u - Eu) + \gamma(A - EA))S] \\
&= E[Su] - E[S]E[u] + \gamma E[SA] - \gamma E[A]E[S] \\
&= \gamma \cov(A,S)\\
\end{align}$$So unless I think ability and schooling have nothing to do with each other - or ability has nothing to do with earnings - $\beta_1$ won't be the actual relationship I want (see [[Econometrics 551 II - Regression I#Omitted Variable Bias|Omitted Variable Bias]] for more detail). OLS will be inconsistent. 


### Schooling Instrument

```ad-important
title: Valid Instrument 


Suppose some variable $Z$ satisfies the following conditions: 

1) <font color=gree>Instrument Relevance</font>: $\cov(Z, S) \neq 0$ 
2) <font color=gree>Exogeneity</font>: $E[Ze] = 0$. 

Then $Z$ is a <font color=gree>valid instrument</font> for X.
```

Relevance is testable - simply look at it. But exogeneity is not. 

$$\begin{align}
E[Y - \beta_0 - \beta_1S] &= E[e] = 0 \text{ by construction } \\
E[ Z(Y - \beta_0 - \beta_1 S)] &= 0 \text{ exogeneity }\\
\end{align}$$ 
From the first expression we can remove $\beta_0$. 
$$\begin{align}
\beta_0 &= E[Y] - \beta_1 E[S]\\
0&= E[Z((Y - EY) - \beta_1(S - ES))] \\
0&= E[Z(Y - EY)] - \beta_1E[Z(S - ES)] \\
\beta_1 &= \frac{\cov(Z, Y)}{\cov(Z,S)}
\end{align}$$

Note the difference between this and an OLS on $Z$. 

### Simultaneity
Another use case - we can think of this as a form of exogeneity, but it has its own rich history as a problem. 

A market has the following demand and supply schedules, as functions of clearing price $\tilde P$:

$$ Q^d = \beta_0^d + \beta_1^d \widetilde P + e^d $$
$$ Q^s = \beta_0^s + \beta_1^s \widetilde P + e^s $$
where $E[e^s] = E[e^d] = E[e^se^d] = 0$. $P$ and $Q$ are observable, with $Q = Q^s(P) = Q^d(P)$ - the market clears. This gives us an expression for that price: 

$$\begin{align}
Q^d(P) &= Q^s(P)\\
\beta_0^d + \beta_1^d P + e^d &=  \beta_0^s + \beta_1^s  P + e^s \\
(\beta_1^d - \beta_1^s)P &= \beta_0^s - \beta_0^d + e^s - e^d\\
P &= \frac{\beta_0^s - \beta_0^d + e^s - e^d}{\beta_1^d - \beta_1^s}
\end{align}$$
So: 
$$\begin{align}
E[Pe^s] &= E\left[\frac{\beta_0^s - \beta_0^d + e^s - e^d}{\beta_1^d - \beta_1^s}e_s\right]\\
&= \frac{1}{\beta_1^d - \beta_1^s}\left(E\left[(e^s)^2] - E[e^d e^s\right] + (\beta_0^s - \beta_0^d\right)E[e^s])\\
&= \frac{E[(e^s)^2]}{\beta_1^d - \beta_1^s}\\
&= \frac{\var(e^s)}{\beta_1^d - \beta_1^s}\\
E[Pe^d] &= \frac{\var(e^d)}{\beta_1^s - \beta_1^d}
\end{align}$$

#### Instrument Approach

Suppose an instrument $Z$ that moves supply but not demand. I can use this as a lever for the estimation of the $\beta$ parameters. (What would such a thing look like? Whether I have one or not needs to be based on a 'story'). 

So 

$$ Q^s = \beta_0^s + \beta_1^s P + \beta_2^s Z+  e^s$$ with $E[e^sZ] = E[e^dZ] = 0$. 
Then 
$$ P = \frac{\beta_0^s - \beta_0^d + \beta_2^sZ + e^s - e^d }{\beta_1^d - \beta_1^s}$$

In other words, price is linear in $Z$: 

$$\cov(P,Z) = \frac{\beta_2^s}{\beta_1^d - \beta_1^s}$$
assuming $\beta_2^S$ nonzero. 

So now to find our $\beta_1^d$, use the fact that $E[Ze^d] = 0$: 
$$\begin{align}
E[Ze^d] &=\frac{1}{\beta_2^s} E[e^d\left((\beta_1^d - \beta_1^s)P -  (\beta_0^s - \beta_0^d + e^s -e^d)\right)]\\
& =\frac{\beta_1^d - \beta_1^s}{\beta_2^s} E[e^dP] -  E[e^d(\beta_0^s - \beta_0^d + e^s -e^d)]\\
& =\left(\frac{\beta_1^d - \beta_1^s}{\beta_2^s}\right)\left( \right) -  E[e^d(\beta_0^s - \beta_0^d + e^s -e^d)]\\
& =

\end{align}$$


```ad-note
title: Aside

'LATE' style IV: no sense of a correct specification of the outcome model, i.e. no functional form. But there is a functional form at the first stage - vs traditional form involves assumptions about the second stage. 

```
