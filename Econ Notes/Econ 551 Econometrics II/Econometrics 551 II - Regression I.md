---
aliases:
creation date: Friday, February 17th 2023, 11:12 am
date updated: Sunday, February 19th 2023, 1:38 pm

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
We can also call this the <font color=gree>linear projection</font> of $Y$ onto $X$. A BLP is sometimes written $L(Y|X)$ or $\mathbf{L}(Y|X)$


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

## Omitted Variable Bias


### Motivating Example: Wages and Human Capital

Model from Grilliches 1977. 

$$Y = p_H H\exp[u]$$
Earnings are price of human capital $p_H$ times human capital times random things $e^u$. 

$$H = \exp[\beta_1 S]\exp [\gamma A]$$
$S$ is schooling. $\beta_1$ is the 'structural' parameter we're interested in. $A$ is unobserved ability (or anything else unobserved that affects $H$). $Y$ and $S$ are observable: $p_H$, $H$, $A$, $u$, are not. 

Now we can take logs: 

$$\begin{align}
\log Y &= \log p_H +\log H + u\\
&=  \log p_H + \beta_1S + \gamma A + u\\
&= E\log p_H + Eu + \beta_1 S + \gamma A + (u - Eu)+ (\log p_H - E\log p_H)\\
&= \beta_0^* + \beta_1S + \gamma A + e^*\\
\end{align}$$

In this, all we've done is isolate $S$ and $A$ which are of interest, changing the others into either effects on $EY$ (the two expectations) or $\var (Y)$ (the two last terms). $E(e^*) = 0$. We can also use the above to evaluate $E[e^*S]$ and $E[e^*A]$ for our BLPing. If $u$ and $\ln p_H$ are independent of $A,S$ then we're off to the races: 

$$L(\log Y | (1, S , A)) = \beta_0 + \beta_1 S + \gamma A$$
What if we did a regression that bundled $A$ in with the other stuff? 
$$
\begin{align}
\log Y &= \log p_H +\log H + u\\
&= \log p_H + \beta_1S + \gamma A + u\\
&= E\log p_H + Eu + \gamma EA + \beta_1 S + (u - Eu)+ (\log p_H - E\log p_H) + \gamma(A - EA)\\
&= \beta_0 + \beta_1S + e\\
\end{align}
$$

Here, $\beta_0 = \beta_0^* + \gamma EA$, and $e = e^* + \gamma (A - EA)$. So $E[e] = 0$. But 
$$\begin{align}
E[eS] &= E[(e^* + \gamma (A - EA))S] \\
&= E[e^*S] + \gamma E[(A - EA)S]\\
&= \gamma E[AS - EAS]\\
&= \gamma (E[AS] - E[A]E[S])\\
&= \gamma \cov(A,S)
\end{align}$$
So this is only $0$ if $\gamma = 0$ (a silly case) or $\cov(A,S) = 0$. Otherwise, what will happen? 

$$\begin{align}
\hat \beta &= E[SS']\inv E[SY]\\
&= E[SS']\inv E[S(S'\beta_1  + e)]\\
&= E[SS']\inv (E[SS'] \beta_1  + E[eS]\\
&= \beta_1 + \gamma \cov(A,S)/\var(S)\\ 
\end{align}$$
so it's biased upward. 



## Subvectors of $\beta$


Let $X \in \R^k$ with $E[XX']$ invertible, $Y = X'\beta + e$, $E[eX] = 0$, $\beta = (E[XX'])\inv E[YX]$

We can partition $X$ into $X_1, X_2$ and $\beta$ into $\beta_1, \beta_2$. Then 

$$ Y = X_1'\beta_1 + X_2'\beta_2 + e$$ with 
$$E[Xe] = E\left[ \begin{pmatrix} X_1 \\X_2\end{pmatrix}e\right] = 0$$
Then dividing up the formula for $\beta$ gets us 

$$ \begin{bmatrix} 
\beta_1 \\ \beta_2 
\end{bmatrix} =
\begin{bmatrix} 
E[X_1 X_1'] & E[X_1X_2']\\
E[X_2X_1'] & E[X_2 X_2']\\
\end{bmatrix} \inv 
\begin{bmatrix} 
E[X_1 Y] \\
E[X_2 Y]
\end{bmatrix}$$


There are two approaches to finding this: 
1) Partitioned Matrix Inverse, and 
2) iterated projection

### Partitioned Matrix Inverse
#status/section/🚧 

### Iterated Projection

#### Theorem

With $Y = X_1'\beta_1 + X_2'\beta_2 + e$, 
Let 

$$\tilde Y = Y - L(Y|X_2)$$
$$ \tilde X_1 = X_1 - L(X_1|X_2)$$
$$ \tilde Y = \tilde X_1'\tilde \beta_1 + \tilde e$$ where $E[e\tilde X_1 ] =0$. Then $\tilde \beta_1 = \beta_1$. 

```ad-note
title: Geometric Intuition

Recall that $X\beta$ is the projection of $Y$ onto the column space of $X$, see [[Strang 16. Least squares approximations]]. The projection matrix is $X'(XX')\inv X$, so $PY = \hat Y$. 

In this step, we determine two projection matrices: $Q$ projects $Y$ onto $X_2$ and $R$ projects $X_1$ onto $X_2$. Then what we are doing is projecting $X_1, Y$ onto the left nullspace of $X2$ with $\bar Y = (I - Q)Y$ and $\bar X_1 = (I - R)X_1$ and then seeing the relationship between those. 

The theorem suggests that the projection matrix of $\bar Y$ onto $\bar X$ - the components of $Y$ orthogonal to $X_2$ onto the components of $X$ orthogonal to $X_2$ - is the same as the $X_1$ part of the projection matrix above. 

Given that $X_1$ and $X_2$ are a partition of the entire $X$, this makes sense - we've made them subspaces of $R^k$ with $\dim X_1 + \dim X_2 = k$. 


```


#### Proof

Since $E[XX']$ is invertible, so is its submatrix $E[\tilde X \tilde X']$. 

$$\begin{align}
\tilde \beta_1 &= (E[\tilde X \tilde X']\inv) E[\tilde X \tilde Y]\\
&= (E[\tilde X \tilde X']\inv)( E[\tilde X Y] - E[\tilde X L(Y|X_2)])\\
\end{align}$$
Because $\tilde X_1 \perp L(Y|X_2)$ by construction (and $\tilde X \perp X_2$), our last term goes away:

$$\begin{align}
&= (E[\tilde X \tilde X']\inv)E[\tilde X Y]\\
&= (E[\tilde X \tilde X']\inv)(E[\tilde X X'\beta] + E[\tilde X e])\\
&= (E[\tilde X \tilde X']\inv)(E[\tilde X X_1 \beta_1] + E[\tilde X X_2 \beta_2] + E[\tilde X e])\\
&= (E[\tilde X \tilde X']\inv)(E[\tilde X X_1 \beta_1])\\
&= (E[\tilde X \tilde X']\inv)(E[\tilde X \tilde X']\beta_1 + E[\tilde X L(X_1 |X_2]]\beta_1)\\
&= (E[\tilde X \tilde X']\inv)(E[\tilde X \tilde X']\beta_1\\
&=\beta_1
\end{align}
$$
The result that $X - \bar X$ gives the same regression coefficients as $X$ follows from this, for instance, with $X_2 = 1$. 


## Omitted Variable Bias

A generalized framework for OVB analysis. 