---
aliases:
creation date: Friday, February 17th 2023, 11:12 am
date updated: Friday, February 17th 2023, 5:54 pm

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

Three interpretations of this model. 

### Regression as CEF

Suppose $E[Y|X] = X'\beta$. Then let $e = Y - X'\beta$, so $Y = X'\beta + e$, and $E[e|X]=0$. $E[Y|X] \implies E[e|X]=0$ and vice versa. This is a model of the CEF with $e$ as a deviation from the CEF. 

As a consequence of $E[e|X] = 0$ we have also that $E[eX] = 0$ and $E[e]=0$, both of which can be found with LIE. 

The implication is that $\beta  = \arg min_{b \in \R^k}E[(Y-X'b)^2]$, using the parametric family concept. This is a convex optimization problem, we can solve with the FOC as in [[2002.6 Regression - Matrix Treatment]] to get the unique soln 

$$ \beta = (E[XX'])\inv E[XY]$$ 
Note here that $X$ and $\beta$ are both $1 \times K$ random vectors! So $X'\beta$ is $1\times 1$, and so is $Y$. We're still operating at the population level. 

### Regression as BLP

Let $Y \in \R$, $X \in \R^k$, $\beta \in \R^k$. $X_0 = 1$; $E[X'X]$ has full rank. Assume $EY^2 < \infty$. 

Define $\beta$ as $\arg min_{b \in \R^k}E[(Y-X'b)^2] = \arg min_{b \in \R^k}E[(E[Y|X]-X'b)^2]$, and define $e = Y - X'\beta$.  So what $\beta$ is telling us is the <font color=gree>best linear predictor</font> (BLP) of the CEF $E[Y|X]$. This is without the model assumption that $Y = X'\beta$. 
We can also call this the <font color=gree>linear projection</font> of $Y$ onto $X$. 

Same FOC have same solution: 
$$ \beta = (E[XX'])\inv E[XY]$$

The FOC is the same as saying $E[eX] = 0$; in other words, $E[eX] = 0$ implies that $\beta$ solves the minimization problem. 

We can differentiate $Y$ with respect to covariates $X$ to get partial or marginal effects. 

We say $X$ is <font color=gree>exogenous</font> if $E[eX]=0$, and $X$ is <font color=gree>endogenous</font> if $E[eX]\neq 0$. Worry a lot about exogeneity, which will make the BLP differ from the CEF. 


``` ad-note
title: $E[eX] = 0$ vs $E[e|X]=0$

- $E[e|X] = 0$, implies that $E[eX] = 0$. The latter is not true. Many counterexamples can be given: a simple one is $\text{supp} (X) = \{0,1\}$, and $e = 1-X$. Then $eX = (1-X)X$ which is $0$ always; but $E[e|X=x] = 1-x \neq 0$. 
- The latter is a sufficient condition to ensure that $X'\beta$ is the BLP of the CEF.
- $E[e|X] = 0$ can tell us the much more powerful fact that $m(X)$ is the CEF of $X$, as shown above. 



```

## Problems with Linear Regression

### Measurement Error

One way the BLP and CEF can differ is in measurement error. 

Suppose $Y = (X^*)' + e^*$, and $Ee^*X = 0$. But the researcher can't see $X^*$ and $e^*$. They only see $X = X^* + v$ ; we might say that $X^*$ is latent and measured with error. 

Assume $Ev = 0$ and $Evv' < \infty$, with $v \indep Y, X^*$ -called 'classical measurement error'. It follows that $v \indep e^*$. What do I need to say that measurement error doesn't screw up my $\beta$? Suffices to ask when I can get $E[Xe] =0$. 

$$\begin{align}
Y &= (X^*)' \beta + e^*\\
&= X'\beta + v'\beta + e^*\\
&= X'\beta + (e^* - v'\beta)\\
X\beta + e &= X'\beta + (e^* - v'\beta)\\
e &= (e^* - v'\beta)\\
\end{align}$$

$$\begin{align}
E[Xe] &= E[(X^* + v)(e^* - v'\beta)]\\
&= E[X^*e^* + ve^* - = X^*v\beta + vv'\beta]\\
&= E[X^*e^*] + E[ve^*] - E[X^*v\beta] + E[vv'\beta]]\\
&= - E[X^*v]\beta + E[vv'\beta]]\\
\end{align}$$
So this requires either $\beta = 0$, or $Evv' = 0$ meaning that $v$ has $0$ variance; ie $v$ is $0$. 


Can show that the linear projection coefficient on $X_j$, a covariate that has measurement error, will be biased towards $0$. 


### Interval-Censored Outcomes

[[Manski and Tamer 2002 Inference on Regressions with Interval Data on a Regressor or Outcome|Manski and Tamer 2002]]. If we want to learn about variables of interest in the presence of missing data, we can establish a weaker form of identification (with 'identification' to be defined later) - "Set Identification".

Suppose $Y = X'\beta + e$ and $E[eX] = 0$. Some observations are missing either in part or in full. If $S$ is an index for completeness of observations, $E[eX|S=1]\neq 0$ if $S$ is not totally random with respect to $X$ and $Y$. 

This can take the form of <font color=gree>censoring</font> or <font color=gree>truncation</font>: 
- Censoring is when some $X_i$ or $Y_i$ is missing in whole or part
- Truncation is when whole observations are selected into or out of the data set. 

``` ad-note 
title: Disciplinary Aside 

The relationship between missing data and inference is complicated and an object of disciplinary conflict. Example: In the early 20th century, women's labor market participation (a common topic of study) was inversely related to education. More educated or higher-status women did not work. Traditional labor economists would say they had higher 'reservation wages', ie. the hurdle a market wage would have to clear to lure them into the market. 

There's a tendency of statisticians to be totally confused by this. What is a reservation wage? Can it ever be clearly observed? This is the foundation of Don Rubin's distinction between potential outcomes and missing data. 

Potential outcomes in the case of a vaccine are very clear: what happens if the vaccine is administered to me? Easy to imagine someone coming up to me and sticking needle in my arm. But what about the potential outcome of my wage if I was black, or female? There's no clean (unbundled) treatment that could change these properties of me; so in some sense it's crazy to talk about the causal effects of race or gender. 

[[✒Holland, Paul W.|Paul Holland]] coined a phrase, "No causation without manipulation". In extremis you could say that even an RCT is applicable only to the environment in which it was applied. 


```

## Causality and Models


