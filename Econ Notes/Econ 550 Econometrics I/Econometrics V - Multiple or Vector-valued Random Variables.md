---
aliases:
creation date: Tuesday, October 4th 2022, 12:47 pm
date updated: Friday, November 4th 2022, 11:14 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
---

# [[Econometrics V - Multiple or Vector-valued Random Variables]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 550 Index]]

## Joint Distribution Functions

A random vector is a vector of random variables. The fundamentals are the same: for any $B \in \mathcal B$,
$$P(X \in B) = P_X(B) = P\{\omega \in \Omega: X(\omega) \in B \}$$
Now though we make this claim for $\mathcal B$ in $\R^n$. 

The (cumulative) distribution function is defined element-wise: $F_X(x) = P(X \leq x) = P(X_1 \leq x_1 \cap X_2 \leq x_2 \cap \ldots)$
Again, knowing $F$ gives us $P_X$.

We can also call this the <font color=gree>joint distribution</font> of $x_1, x_2, \ldots$





```ad-example
title: Example in $\R^2$

Suppose $a < b$, $c< d$, and we have $X = X_1, X_2$. Then let $A = (a,b] \times (c, d]$; a square in $\R^2$. Then we can say: 
$$\begin{align}
P(X \in A) &= P(X_1 \in (a, b] \cap X_2 \in (c,d])\\
&= P(X_1 \leq b \cap X_1 > a \cap X_2 \leq d \cap X_2 > c)\\
&= P(X_1 \leq b \cap (X_1 \leq a)^c \cap X_2 \leq c \cap (X_2 \leq d)^c)\\
&= F_{12}(a,c) - F_{12}(b,c) - F_{12}(a, d) + F_{12}(b,d) \\
\end{align}$$

Imagine defining a square as areas below points, ie 'down and to the left'. So: area below top right  corner, minus area below bottom right corner, minus area below top left corner. But then you've double counted so add back the area below the bottom left corner.

```

The density function $f_X(x)$ is $\frac{\partial^n F_X}{\partial x_1 \ldots \partial x_n}$ where $F_X$ is differentiable (which we've said is almost everywhere). This is compatible with the RN-theorem derivative construction based on the measure $P_X$. We can then say that 

$$P_X(X\in A) = \int_A f_X(x_1, \ldots ) dx_1 \ldots dx_n$$
which is an $n-$integral. 

So for the example above, we had $$F_{12}(a,c) - F_{12}(b,c) - F_{12}(a, d) + F_{12}(b,d)$$
which we could then rewrite as 
$$ \int_a^b\int_c^d f_{12}(x_1, x_2) dx_2 dx_1$$
Since this is on a square, [[Fubini's Theorem]] tells us the integrals are interchangeable. 

#### Properties
- $F_X(x) \in [0,1]$
- $F_X(x)$ is non-decreasing in $x$: if $x \leq y$, $F_X(x) \leq F_Y(y)$. 
- $\lim_{\text{ all } x_i \to \infty} F_X(x) = 1$
- $\lim_{\text{ any } x_i \to -\infty} F_X(x) = 0$
- $f_X(x) \geq 0 \; \forall \; x \in \R^n$ 
- $\int_{\Omega_X} f_X(x) dx = 1$
- $f_X$ is measurable
- If an RV is continuous, then $F_X$ is differentiable almost everywhere. 


```ad-info
title: Discrete Case
Discrete random vector has set $C$ such that $P(X \in C) =1$ and $C$ countable. Probability of any countable set is 

$$P(x \in A) = \sum_{x_i \in A} f_X(x_i)$$

```

## Marginal Distributions

I may be interested in a <font color=gree>marginal</font> or unconditional probability that $X_i = x$. Easiest to think about in the discrete two-variable case. Given some joint distribution $f_{X,Y}$, what is $P(X = x)$? If $Y$ takes on values $y_1, \ldots, y_n$, then I can say that 

$$\begin{align}
P(X = x) &= P(X = X \cap Y \in \Omega_Y)\\
&= P\left(X = x \cap \bigcup (Y = y_i)\right) \\
&= P\left(\bigcup (X =x \cap Y = y_i)\right)\\
&= P(X = x \; \cap \; Y = y_1) + P(X=x \; \cap \; Y = y_2) + \ldots
\end{align}$$
This is looking at the probability that $X =x$ under all possible conditions on $Y$. 

We can then generalize this to a continuous case. 
$$\begin{align}
f_X(x) &= \frac{d}{dx} F_X(x)\\
&= \frac{d}{dx}P(X \leq X)\\
&= \frac{d}{dx} P(X \leq x \cap Y \in \Omega_Y)\\
&= \frac{d}{dx} \int_{-\infty}^x\int_{-\infty}^\infty f_{XY}(a,b) da db\\
&= \frac{d}{dx} \int_{-\infty}^\infty f_{XY}(x,b) db\end{align}$$
Think of this as 'integrating out' the $Y$ from the joint distribution. 


#### Notes
- The joint gives you the marginals. But the marginals don't give you the joint, except in the case of independence. 
- Can get the marginal (c)df $F_X(x) = \lim_{y\to\infty} F_{XY}(x,y)$:

$$\begin{align}
\lim_{y\to\infty} F_{XY}(x,y) 
&= \lim_{y\to\infty}\int_{-\infty}^y \int_{-\infty}^x f_{XY}(u,v) du dv \\
&=\int_{-\infty}^\infty \int_{-\infty}^x f_{XY}(u,v) du dv\\
&=\int_{-\infty}^x \int_{-\infty}^\infty f_{XY}(u,v) du dv\\
&= \int_{-\infty}^x f_X(u)du \\
&= F_X(x)
\end{align}$$

Here I use Fubini's Theorem to switch the integrals around. 

### Independence

Extend our previous independence concept. We had defined independent events: $A \indep B \iff P(A \cap B) = P(A)P(B)$. We then defined random variables as independent if $P(X \in A, Y \in B) = P(X \in A)P(Y \in B)$. 

Now we can say random variables $X$ and $Y$ are independent if $F_{XY} = F_XF_Y$. This is straightforward: $F_{XY}(x,y) = P(X \in (-\infty, x] \cap Y \in (-\infty, y]) = P(X \in (-\infty, x])P(Y \in (-\infty, y]) = F_X(x)F_Y(y)$. 

We can differentiate: 

$$\begin{align}
f_{XY}(x,y) &= \frac{d^2}{dxdy}F_{XY}(x,y) \\
&= \frac{d^2}{dxdy}F_X(x)F_Y(y) \\
&= \frac{d}{dy}F_Y(y)f_X(x)\\
&= f_Y(y)f_X(x)\\
\end{align}$$
Either of these conditions offer convenient ways to check if two RVs are independent: they are true iff independence

Proof: in discrete case, let $D = \{ x_i\}, G = \{ y_i\}$ arbitrary sets.
$$\begin{align}
P(X\in D, Y \in G) &= P\left(X \in \bigcup_i \{x_i\}, Y \in \bigcup_j \{ y_j\}\right)\\
&= \sum_i P\left( X \in \{x_i\}, Y \in \bigcup_j \{ y_j\} \right)\\	
&= \sum_i \sum_j P\left( X \in \{x_i\}, Y \in \{ y_j\} \right)\\	
&= \sum_i \sum_j f_{XY}(x_i, y_j) \\
&= \sum_i \sum_j f_{X}(x_i)f_Y(y_i) \\
&= \sum_i f_{X}(x_i) \sum_j f_Y(y_i) \\
&= P(X = x, Y= y)
\end{align}$$

#### Functions of Independent RVs
If $X,Y$ are independent then $g(X), h(Y)$ are independent. Intuitively, knowing $g(X) = x$ is weakly less information than knowing $X =x$ (cannot be more). 

Proof: 
Let $A \in \Omega_g, B \in \Omega_h$. Then: 
$$\begin{align}
P(g(X) \in A \cap h(Y) \in B) &= P(X \in \{x: g(x) \in A\} \cap Y \in \{y:h(y) \in B\})\\
&= P(X \in \{x: g(x) \in A\})P( Y \in \{y:h(y) \in B\})\\
\end{align}$$

The information idea is reflected in the fact that $\{y:h(y) \in B\}$ has weakly more elements/greater measure than $B$. 


## Expectation

The expectation of a random vector $(X_1, \ldots, X_n)$ is $(EX_1, \ldots, EX_n)$. From this definition:
- If $g:\R^n \to \R^m$, then $E(g(X)) = (Eg_1(X), \ldots, Eg_m(X))$
- $E(X + Y) = EX + EY$
- $E(cX) = cEX$
- $E(\underset{m \times n}{A}x + \underset{m\times 1}b) = AEX + b$. 

We can use a form of the above. Let $g(X,Y) = (X - \mu_X)(Y - \mu_Y)$.

#### Covariance

The <font color=gree>covariance</font> is $\sigma_{XY} = Eg(X,Y) = E[(X - \mu_X)(Y - \mu_Y)] = EXY - EXEY$. If $X,Y$ are independent: 
$$\begin{align}
EXY &= \int \int xy f_{XY}(x,y)dxdy\\
&= \int \int xf_X(x)yf_Y(y)dxdy \\
&= \int xf_X(x)dx \int yf_Y(y)dy \\
&= EXEY
\end{align}$$
so the covariance is zero. 

The covariance can be normalized to get a <font color=gree>correlation coefficient</font>: 

$$\rho_{XY} = \frac{\sigma_{XY}}{\sigma_X\sigma_Y}$$
This is invariant to scale and location, and is always in $[-1,1]$. To show the latter, use the [[Econometrics VI - Inequalities and Important Results#Cauchy-Bunyakovsky-Schwarz Inequality|CBS Inequality]]. 



```ad-warning
title: 

NOTE: Independent means zero covariance. Zero covariance does NOT mean independence!! 

Example: $x,y$ where $y = g(x) \epsilon$, $E\epsilon = 0$, and $\epsilon \indep x$. Then 

$$\begin{align}
EY &= Eg(X)\epsilon\\
&= 0\\
\cov(X,Y) &= E(X - \mu_X)(Y - \mu_Y)\\
&= EY(X-\mu_X)\\
&= E[\epsilon g(X)(X - \mu_X)]\\
&= E\epsilon g(X)X - E\epsilon g(X) EX \\
&= E\epsilon (Eg(X)X - E g(X) EX)\\
&= 0
\end{align}$$

But $X,Y$ are obviously (super) dependent.

```

#### Variance of $X + Y$

The variance of $X + Y$ can be found as follows: 

$$\begin{align}
\var (X+Y) &= E[(X + Y)^2 - [E(X+Y)]^2]\\
&= E[X^2 + 2XY + Y^2 - EX^2 - EY^2 - 2EXEY]\\
&= E[X^2] - EX^2+ E[Y^2] - EY^2+ 2E[XY] - 2EXEY\\
&= E[(X - EX)^2] + E[(Y-EY)^2] + 2E[(X-EX)(Y - EY)]\\
&= \var(X) + \var(Y) + 2 \cov(X,Y)\\
\end{align}$$
So when $X$ and $Y$ are independent, $\var(X +Y ) = \var (X) + \var (Y)$; if all $n$ of the $X_i$ are mutually independent, then 
$$ \var\left(\sum_{i=1}^n X_i\right) = \sum_{i=1}^n \var(X_i)$$
If $X_1, \ldots, X_n$ are iid and have variance $\sigma^2_X$ then $\var (\sum_{i=1}^n X_i/n) = \sigma_X^2/n$.

More generally, if $X_1, \ldots, X_n$ are not independent, then 

$$\begin{align}
\var\left(\sum_{i=1}^n X_i \right) &= E\left[ \left( \sum_{i=1}^n X_i - E\sum_{i=1}^n X_i\right )^2 \right]\\
&= E\left[ \left( \sum_{i=1}^n X_i\right)^2 \right] - \left(E\sum_{i=1}^n X_i\right)^2\\
&= E\left[ \sum_{i=1}^n X_i^2 + \sum_{i=1, i \neq j}^n \sum_{j=1}^n X_iX_j \right] - \sum_{i=1}^n EX_i^2 - \sum_{i=1, i \neq j}^n \sum_{j=1}^n EX_iEX_j \\
&= \sum_{i=1}^n \var(X_i)+ \sum_{i=1, i \neq j}^n\sum_{j=1}^n \cov(X_i,X_j)\\
\end{align}$$
```ad-example
title:Sample Mean

Define the sample mean as 
$$\overline X_n = \sum_{i=1}^n X_i $$
Then following the above logic: 
$$\var(\overline X_n) = \frac{1}{n}\sum_{i=1}^n \var(X_i)+ \frac{1}{n^2}\sum_{i=1, i \neq j}^n\sum_{j=1}^n \cov(X_i,X_j)$$

One desirable property of an estimator is convergence. Will the sample mean converge as $n\to \infty$? That'll require some conditions on $\cov(X_i, X_j)$ so that it doesn't grow faster than $n^2$. For instance, when working with time series one might say that $\cov(X_i, X_i)$ falls off rapidly when going further back in time. This could let me bound the growth in covariance. 


```


## Variance/Covariance For Random Vectors

A generalization of the above results. Suppose $X = (X_1, \ldots X_n)$. 

Then define
$$\begin{align}
\var(X) &= E[(X - EX)(X - EX)']\\
\end{align}$$
It follows that 
$$\begin{align}
\var(X)_{i,j} &= E(X_iEX_i)(X_j-EX_j)' \\
&= \cov(X_i, X_j)\\
\var(X)_{i,i} &= E(X_iEX_i)(X_i-EX_i)' \\
&= \var(X_i)\\
\end{align}$$
This matrix is symmetric by the symmetry of the covariance. It is positive semidefinite: 

$$\begin{align}
c'\var(X) c&= E[c'(X - EX)(X - EX)'c]\\
&= E[(c'(X-EX))(c'(X-EX))']\\
&= E[c'(X-EX)^2]
\end{align}$$
The last item is definitely a positive quantity. In that step I use the fact that $c'(X - EX)$ is $1 \times n \cdot n \times 1$ and so a scalar. 

A covariance matrix is nether PSD nor symmetric. In fact it doesn't even have to be square. It's defined as 
$$\begin{align}
\cov(X,Y) &= E[(X - EX)(Y - EY)]\\
\end{align}$$
So 
$$\begin{align}
\cov(X,Y)_{ij} &= E[(X_i - EX_i)(Y_j - EY_j)]\\
&= \cov(X_i, Y_j)\\
\end{align}$$



Some consequences of these definitions: 
1) $\var(X + b) = \var(X)$
2) $\var(AX + c) = A\var(X)A'$
3) $\var(X+ Y) = \var(X) + \var(Y) + \cov(X,Y) + \cov(Y,X)$
4) $X,Y$ independent vectors: then $\var(X + Y) = \var(X) + \var(Y)$
5) $\cov(AX + b, CY + d) = A\cov(X,Y)C'$
6) $\cov(X + Y, Z) = \cov(X,Z) + \cov(Y, Z)$

These results can be proved elementwise according to Don. 


## Conditional PDF and PMF

### PMF

Let $X, Y$ be discrete random variables, with sample space $\Omega_X$ and $\Omega_Y$. Let $A$ and $B$ be events in $\Omega_X$ and $\Omega_Y$. 

$$ P(X \in A|Y \in B) = \frac{P(X \in A \cap Y \in B)}{P(Y \in B)}$$

We can thence create a conditional PMF: 

$$ f_{X|Y}(x|y) = P(X = x|Y =y) = \frac{P(X=X \cap Y = y)}{P(Y = y)} = \frac{f_{XY}(x,y)}{f_Y(y)}$$
for nonzero $f_Y$. You can then combine with others as you please, to get eg. $P(X \in A|Y = y)$. 

### PDF
This one we'll work backwards from a desirable property. We want independent random variables to be such that 

$$ X \indep Y \to f_{X|Y}(x|y) = f_X(x)$$
We know already that $f_{XY}(x,y) = f_X(x)f_Y(y)$. So define 

$$f_X(x) = \frac{f_{XY}(x,y)}{f_Y(y)} = f_{X|Y}(x,y)$$
This intuitively makes sense, in that it maps to the event level definition. It'll make even more sense when we start integrating, or conceptualizing this with areas. 

Properties:
1) $f_{X|Y}$ is nonnegative. 
2) $f_{X|Y}$ integrates to 1:
	$$\begin{align}
	\int_{-\infty}^\infty f_{X|Y y}(x) dx &= \int_{-\infty}^\infty f_{X|Y=y}(x)dx \\
	&= 	 \int_{-\infty}^\infty \frac{f_{XY}(x,y)}{f_Y(y)}dx \\
	&= \frac{1}{f_Y(y)}\int_{-\infty}^\infty f_{XY}(x,y)dx \\
	&= \frac{f_Y(y)}{f_Y(y)}\\
	&= 1
	\end{align}$$
	
We can now use this to compute 
$$P(X \in A | Y = y) = \int_G f_{X|Y=y}(x)dx = \frac{1}{f_{Y}(y)}\int_G f_{XY}(x,y)dx $$
This gets us also a conditional expectation
$$ E(X|Y = y) = \frac{1}{f_Y(y)}\int_{\Omega_X} xf_{XY}(x,y)dx$$
Note: there's no direct event-based constrution of the above. <font color=#F7B801>though perhaps there's one based in intervals and with limits</font>

### LIE/Law Of Iterated Expectation
![[2002.1 Probability#Law of Iterated Expectation]]


## Multivariate Normal (MVN/MN)

### Definition

Define $\mu \in \R^n$ and $\underset{n\times n}{\Sigma}$ be positive semidefinite and symmetric. Then $X = (X_1, \ldots, X_n) \sim \mathcal{MVN}(\mu, \Sigma)$ if, for real $x$,
$$f(x) = \frac{1}{(2\pi)^{n/2}} (\det \Sigma)^{-1/2} \exp\left[ -(1/2)(x - \mu)'\Sigma\inv (x-\mu)\right] $$
Just as a check: $x - \mu$' is $1 \times n$, $x - \mu$ is $n\times 1$, so this all shakes out to a scalar. 

Every MVN has a unique $\mu, \Sigma$. 


### Standard Normal-ification
We can demonstrate that that the multivariate normal is the product of standard normals. 
#### Spectral Decomposition
Linear algebra tells us that since $\Sigma$ is PSD and symmetric, then we can write 
$$ \Sigma = B \Lambda B'$$
where $\Lambda$ is $n \times n$ diagonal (with diagonal = eigenvalues of $\Sigma$), and $B$ is orthogonal meaning $B'B = I$, with the columns of $B$ being eigenvectors of $\Sigma$. Write $\Lambda^p$ for each diagonal element raised to the $p$.. 

With this we can create square roots of $\Sigma$: 

$$ \Sigma^{1/2} = B\Lambda^{1/2}B'\text{ and } \Sigma^{-1/2} = B\Lambda^{-1/2}B'$$
In other words: diagonalize, take sqrt, de-diagonalize
So 
$$\begin{align}
\Sigma^{1/2}\Sigma^{1/2} &= B\Lambda^{1/2}B' B\Lambda^{1/2}B' \\
&= B\Lambda^{1/2}\Lambda^{1/2}B' \\
&= B\Lambda B'\\
&= \Sigma\\
\Sigma^{-1} &= (B\Lambda B')\inv \\
&= B'\inv \Lambda\inv B\inv \\
&= B \Lambda\inv B'\\
\Sigma^{-1/2}\Sigma^{-1/2} &= \Sigma^{-1}\\
\end{align}$$
#### Decomposition of MVN

With this tool, we can write $Z = \Sigma^{-1/2}(X - \mu)$. A change of variables result gives us that $dz = (\det \Sigma)^{-1/2}dx$ 
Then we find that 
$$\begin{align}
f_Z(z) &= \frac{1}{(2\pi)^{n/2}}\exp\left[-(1/2)z'z\right]\\
&= \prod_{i=1}^n\frac{1}{(2\pi)^{1/2}}\exp\left[-(1/2) z_i^2\right]
\end{align}$$
which is the product of $n$ standard normals: $Z \sim \mathcal N(0,I_n)$. Then 
$X = \Sigma^{1/2} Z + \mu$ and $EX = E(\Sigma^{1/2}Z + \mu) = \mu$.
$$\begin{align}
\var(X) &= \var(\Sigma^{1/2}Z + \mu) \\
&= \Sigma^{1/2} \var(Z) (\Sigma^{1/2})' \\
&= \Sigma^{1/2} I_n \Sigma^{1/2}\\
&= \Sigma
\end{align}$$
using the fact that $\Sigma^{1/2}$ is symmetric. 

I can also go backwards to show that $\Sigma^{1/2} Z + \mu$ is an MVN, provided that $\Sigma$ is positive semidefinite <font color=#F7B801>and symmetric?</font>

### MVN Marginals and Conditionals

#### Marginals

From the above, we can observe that any linear transformation of MVNs is an MVN also. 

Suppose $\underset{n \times 1}{X} \sim \mathcal N(\underset{n \times 1}{\mu}, \underset{n \times n}{\Sigma})$. We're interested in some subset of the $X$, $X_1$; so we can break $X$ up: $X = \begin{bmatrix} X_1\\X_2\end{bmatrix}$. Then $X_1 \in \R^{n_1}, X_2 \in \R^{n_2}$, and $n_1 + n_2 = n$. 

We can write $X_1$ as a linear transformation of $X$: 
$$X_1 = \begin{bmatrix} I_{n_1} & \underset{n_1 \times n_2}{0}\end{bmatrix}X$$
This matrix - call it $G$ - is positive definite. So since we've found $X_1$ is a linear transformation of $X$ it follows that $X_1 \sim \mathcal N (\mu', \Sigma')$. We just have to find $\mu'$ and $\Sigma'$ to characterize $X_1$. 

The mean is straightforward. 

$$\begin{align}
\mu' &= E\left [GX\right]
\\&= \begin{bmatrix} I_{n_1} & \underset{n_1 \times n_2}{0}\end{bmatrix} E[X] \\
&= (\mu_1, \ldots, \mu_{n_1}, \underset{1 \times n_2}{0, \ldots, 0})
\end{align}$$
Call this $\mu_1$; note that $\mu = \begin{bmatrix} \mu_1' & \mu_2' \end{bmatrix}'$. Variance is more complex. First break $\Sigma$ into a block matrix for convenience.
$$\begin{align}
\Sigma &= \begin{bmatrix} \underset{n_1\times n_1}{\Sigma_{11}} & \underset{n_1\times n_2}{\Sigma_{12}} \\
 \underset{n_2\times n_1}{\Sigma_{21}} & \underset{n_2\times n_2}{\Sigma_{22}}\end{bmatrix}\\
\Sigma' &= \var(GX) \\
&= G\var(X)G'\\
&= \begin{bmatrix} I_{n_1} & \underset{n_1 \times n_2}{0}\end{bmatrix}\Sigma \begin{bmatrix} I_{n_1} \\ \underset{n_2 \times n_1}{0}\end{bmatrix}\\
&= \begin{bmatrix} I_{n_1} & \underset{n_1 \times n_2}{0}\end{bmatrix}\begin{bmatrix} \underset{n_1\times n_1}{\Sigma_{11}} & \underset{n_1\times n_2}{\Sigma_{12}} \\
\underset{n_2\times n_1}{\Sigma_{21}} & \underset{n_2\times n_2}{\Sigma_{22}}\end{bmatrix} \begin{bmatrix} I_{n_1} \\ \underset{n_2 \times n_1}{0}\end{bmatrix}\\
&= \begin{bmatrix} I_{n_1} & \underset{n_1 \times n_2}{0}\end{bmatrix}
\begin{bmatrix} \underset{n_1\times n_1}{\Sigma_{11}} & \underset{n_1\times n_2}{0} \\
\underset{n_2\times n_1}{\Sigma_{21}} & \underset{n_2\times n_2}{0} \end{bmatrix}\\
&= \begin{bmatrix}\underset{n_1\times n_1}{\Sigma_{11}} & \underset{n_1\times n_2}{0} \\
\underset{n_2\times n_1}{0} & \underset{n_2\times n_2}{0}\end{bmatrix}
\end{align}$$
So we can write $X_1 \sim \mathcal N(\mu_1, \Sigma_{11})$ and similarly $X_2 \sim \mathcal N(\mu_2, \Sigma_{22})$.

It's clear that $X_1 \indep X_2$ implies $\Sigma_{12} = 0$. 

We can show that $\Sigma_{12} = 0$ necessitates $X_1 \indep X_2$. Recall that independence means $f_{XY}(x,y) = f_X(x)f_Y(y)$. So, first the determinant of $f_{XY}$:

$$\begin{align}
(x - \mu)'\Sigma\inv(x-\mu) &= \begin{bmatrix}x_1 - \mu_1 \\ x_2- \mu_2  
\end{bmatrix}'\begin{bmatrix} 
\Sigma_{11} & \Sigma_{12}\\
\Sigma_{21} & \Sigma_{22}\\
\end{bmatrix}
\begin{bmatrix} 
x_1 - \mu_1 \\ x_2- \mu_2  
\end{bmatrix}
\\
&= \begin{bmatrix}x_1 - \mu_1 \\ x_2- \mu_2  
\end{bmatrix}'\begin{bmatrix} 
\Sigma_{11} & 0\\
0 & \Sigma_{22}\\
\end{bmatrix}
\begin{bmatrix} 
x_1 - \mu_1 \\ x_2- \mu_2  
\end{bmatrix}\\
&= (x_1 - \mu_1)'\Sigma\inv(x_1-\mu_1) (x_2 - \mu_2)'\Sigma\inv(x_2-\mu_2)\\ 
\end{align}$$
Then the density: 
$$\begin{align}
f(X) &= \frac{1}{(2\pi)^{n/2}} (\det \Sigma)^{-1/2} \exp\left[ -(1/2)(x - \mu)'\Sigma\inv (x-\mu)\right] \\
f(\begin{bmatrix} X_1' & X_2'\end{bmatrix}') &= \frac{1}{(2\pi)^{n/2}} (\det \Sigma_{11}\det \Sigma_{22})^{-1/2} \exp\left[ -(1/2)(x - \mu)'\begin{bmatrix} 
\Sigma_{11} & 0\\
0 & \Sigma_{22}\\
\end{bmatrix}\inv (x-\mu)\right] \\
&= f_X(X)f_Y(Y)
\end{align}$$
#### Conditionals
$$\begin{align}
X &\equiv \begin{bmatrix} X_1' & X_2'\end{bmatrix}'\\
E(X_1|X_2 = x_2) &= \mu_1 + \Sigma_{12}\Sigma_{22}\inv(x_2 - \mu_2)\\
\var(X_1|X_2=x_2) &= \Sigma_{11} - \Sigma_{12}\Sigma_{22}\inv\Sigma_{21}
\end{align}$$
Note that the conditional variance doesn't depend on $x_2$; the expectation is linear in $x_2$. Handy.
