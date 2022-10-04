---
aliases:
creation date: Tuesday, October 4th 2022, 12:47 pm
date updated: Tuesday, October 4th 2022, 5:50 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Econometrics V - Multiple or Vector-valued Random Variables]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

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
