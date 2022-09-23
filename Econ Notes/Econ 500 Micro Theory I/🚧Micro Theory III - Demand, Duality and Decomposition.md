---
aliases:
creation date: Friday, September 23rd 2022, 11:46 am
date updated: Friday, September 23rd 2022, 12:29 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[🚧Micro Theory III - Demand, Duality and Decomposition]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Indirect Utility

### Definitions and Properties
#### Basics
For any $p,w$, we can write demand functions $x(p,w)$, the solutions to the utility maximization problem. Define the <font color=gree>indirect utility</font> of $p,w$ to be 
$$ v(p,w) = u(x(p,w))$$
that is, the utility obtained when utility is maximized. 

It's clear that $v$ is homogeneous degree $0$, since $x$ is $HD0$. $v$ must be strictly increasing in $w$ and weakly decreasing in $p$, by the fact of optimization. 

#### Quasiconcavity
We also know that the indirect utility function is [[Micro Theory IIIa - Concave, Convex, Quasi|quasiconvex]], meaning that $v(\lambda x + (1-\lambda)y) \leq \max \{ v(x), v(y) \}$. How? 
- ~~We could make an argument based on diminishing marginal returns. If eg. $p_1$ is very close to $0$ and $p_2$ is not, then maybe $x_2$ is much bigger than $x_1$ and I'd be better off if the prices are similar so that I could do some substitution. ~~
- This is misleading!! We don't require the QCV of $u$ to get QCX of $v$. 

Suppose that bundle $x$ is feasible under some convex combination of prices. Thus $(\lambda p + (1-\lambda) p') x \leq \lambda w + (1-\lambda)w'$. Distributing: $p\lambda x + (1-\lambda)p'x \leq \lambda w + (1-\lambda)w'$. Then I know that either $p \lambda x \leq \lambda w$ or $(1-\lambda)p'x \leq \lambda w'$; in other words, $x$ is feasible in one of the endpoints. So, by walras' law, one of the endpoints is weakly better than $x$. We didn't use quasiconcavity, though we did use monotonicity/local nonsatiation. 

#### Marginal Utility of Income
Using $v$ we can recover the marginal utility of income. 

$$\begin{align}
\partial v(p,w)/\partial w &= \partial u(x(p,w))/\partial w \\
&= \sum_i \frac{\partial u}{\partial x_i} \frac{\partial x_i}{\partial w} \\
&= \lambda \sum_i p_i \frac{\partial x_i}{\partial w} \\
&= \lambda
\end{align}$$
🎉🎉🎉look who it is!!!! 🎉🎉🎉 Our friend the Lagrange multiplier returns at last

The last step there depends on some degree of trickery. When we are at an optimum we can say a lot of differential results go away. This is another [[Envelope Theorem]] style of result, that depends on our maximizing. Mathematically: we know that $px(p,w) = w$, we can differentiate by $w$, and get $\sum p_i (\partial x_i(p,w)/\partial w) = 1$. 

#status/section/🚧 <font color=#F7B801>what's the intuition for this</font>


We can further make transformations: 

$$\begin{align}
\lambda &= \frac{\partial u}{\partial x_i} \frac{1}{p_i} \\
&= \frac{\partial u}{\partial x_i}\frac{\partial x_i(p,w)}{\partial w}\\
\end{align}$$
Here is another perspective on the marginal utility of income. The first step is our old friend the FOC; the second step is another bit of [[Envelope Theorem]] trickery. Specifically, I know that since I am optimizing, I must be indifferent between spending the marginal dollar on all goods. That means, with an incremental change in income, I will spread it over every good, which buys me a quantity equal to $1/p_i$. 


So how could I say that $\lambda = \sum_i\frac{\partial u}{\partial x_i} \frac{\partial x_i}{\partial w}$ but also that $\lambda = \frac{\partial u}{\partial x_i}\frac{\partial x_i}{\partial w}$ for just one good?? 

Once again, because we are maximizing. Also because the latter is in fact an $x(p,w)$. so notation is sloppy.

#### Continuity Proof 1
$v(p,w)$ is continuous. 

Proof: from PS2

Suppose $v(p,w)$ is the utility of $x(p,w)$ that maximizes the problem defined by $p,w$. Suppose continuous $U()$. 

In the limit, $x(p_n, w_n)$ is feasible under $p^*, w^*$. I then know that $\lim U(x(p_n, w_n)) = \lim v(p_n, w_n) \leq v(p^*,w^*)$. 

In the other direction, I want to show that $\lim v(p_n, w_n) \geq v(p^*, w^*)$. 

I know that $p^*x(p^*, w^*) \leq w^*$. Write $(p^* - p_n + p_n)x(p^*, w^*) \leq w^*$. Then $(p^* - p_n)x(p^*, w^*) + p_nx(p^*, w^*) \leq w^*$. Then $p_n x(p^*, w^*) \leq w^* - (p^* - p_n)x(p^*, w^*)$.

I know the latter product goes to zero as $p_n$ converges to $p^*$. Then $x(p^*, w^*)$ is feasible under $p_n, w^*$. Write $w^*$ as $w_n + \epsilon$; then, as $\epsilon \to 0$, $x(p^*, w^*)$ is feasible under $p_n, w_n$; so $v(p^*, w^*) \leq \lim v(p_n, w_n)$. 

#### Continuity Proof 2: Section
We know that $v(p,w) = \max U(x)$ subject to $px \leq w$

Suppose $p_n, w_n$ converge to $p,w$.
Then $\mathcal L_{n \to \infty} v(p_n, w_n) v_c(p,w)$

It's sufficient to show that 

1) $\lim \inf_{n \to \infty} = \lim_{k\to\infty} v(p_n, w_n) \geq v(p,w)$
2) $\lim \sup_{n \to \infty} = \lim_{k\to\infty} v(p_n, w_n) \leq v(p,w)$

For the second. We can say $\lim p_n x(p,w) - w_n \leq 0$. Want to find some bundle that is feasible in $p,w$ that is very close to $p_n, w_n$. 
If we can find such a bundle, we can then use continuity. 

Assume $x_n$ in a bounded set, then we can get a convergent subsequence $x_m \to x_0$, Then we have $p_m x_m \leq w_m$. In the limit this is $p x_0 \leq w$. We know that $U(x_0) = \lim U(x_m) = v(p_m, w_m)$.

We want to establish $v(p,w) \geq U(x_0) = \lim U(x_m) = \lim v(p_m, w_m)$. 

Define subsequence $m$ such that $\lim v(p_m, w_m) = \lim \sup v(p_n, w_n)$. 

$p_m x_m \leq w_m$. Exists some $m$ such that $p_m \geq 1/2p$ and $p_m \leq 2p$. So 

$$px_m \leq 2p_mx_m \leq 2w_m \leq 4w$$ So for sufficiently large $m$ we have $x_m$ in the budget set $p, 4w$. 

#status/section/🚧 

#### Maximum Theorem

Can also prove continuity with a shortcut: the maximum theorem, aka Berge's theorem

Let $u: X \times \Theta \to \R$. We can think of $X$ as endogeneous, $\Theta$ as exogeneous. Can be something like $X$ is commodity space and $\Theta$ is $p,w$. 
Let $B: \Theta \to X$, a continuous, compact-valued correspondence. This can be a budget constraint. 

Then, $v = \max_{x \in B(\theta)}: \Theta \to R$ is continuous in $\theta$ - $p,w$, and the arg-max correspondence (the demand correspondence) is compact-valued, closed, and [[Micro Theory IIIb - Hemicontinuity|upper hemicontinuous]]. 


## Expenditure Minimization and Duality
### Expenditure Minimization Problem

The problem is $\min_{u(x) > \bar u} px$.
Let $u$ be continuous, strictly increasing. Then 
$$ a \in \arg \max_{px \leq w} u(x) \implies a \in \arg\min_{u(x) \geq u(a)}px $$

$$a \in \arg \min_{u(x) \geq \bar u} px \implies a \in \arg\max_{px \leq pa} u(x) $$
The expenditure function $e(p,\bar u) = \min_{x: u(x) \geq \bar u} px$ is homogeneous of degree $1$, strictly increasing in $\bar u$, weakly increasing in $p$.

This turns out to be the same problem as the utility maximization problem when either $\bar u = v(p,w)$ or $w = e(p,\bar u)$. In other words, given some prices, the minimum income you need to attain a certain level of utility is the income for which that utility is the maximum level. 


#### Concavity

The expenditure function is concave in prices. Intuitively, if prices change and the consumption bundle doesn't change, expenditure linearly increases. So substitution must be able to improve on linear increases - hence less-than-linear. 

Let $p'' = \lambda p + (1-\lambda)p'$. We then want to show concavity: that for any value of $\lambda$, $e(p'', u) < \max \{e(p,u), e(p',u)\}$.

Let $x'' \in x(p'', u)$ - exp minimizer under $p''$. Then $e(p'', u)$ is $p''x'' = \lambda p x'' + (1-\lambda)p'x''$. This cannot be greater than both $px''$ and $p'x''$ - so $x''$ must be affordable under one of $p, p'$. But we know that $u(x'') = u$ - so we cannot have both $e(p,u)$ and $e(p',u)$ be greater than $e(p'', u)$, since I could then lower expenditure under one of them by switching to $x''$.

### Hicksian Demand

Our definition of $x(p,w)$ is the vector of consumption maximizing utility given $p,w$. This is the <font color=gree>Marshallian demand</font>, also known as Walrasian or uncompensated demand. 

Define a new demand function, $h(p,u)$:

$$ h(p,u) = \underset{u(x) \geq \bar u}{\arg \min} \; px$$
the expenditure minimizing demand for a utility level $\bar u$. In other words: suppose the prices $p$ were to change (increase) to $p'$. $h$ represents the consumption bundle meeting $\bar u$ while minimizing expenditure under the new price regime. This includes substituting away from more expensive goods/towards cheaper ones. 

This new demand is called the <font color=gree>Hicksian demand</font>, or compensated demand. It has a few immediate properties:
- $h$ is homogeneous of degree 0 in $p$ (i.e. all prices rise by the same factor -> no substitution)
- Convex preferences mean that $h$ is convex (i.e. the indifference curve still can have flat regions). 
- Strictly convex preferences mean that $h$ is SCX, and unique.


For the latter: we want to show that $h$ is convex, i.e.: 
$$ h(\lambda p + (1-\lambda)p', \bar u) \geq \lambda h(p, u) + (1-\lambda)h(p', u)$$
From the definition of $h$ we know that $ph(p,u) = e(p,u)$. Let $p''$ be the convex combination. Then 
$$ e(p'', u) = p''h(p'', u) = \lambda p h(p'',u) + (1-\lambda)p'h(p'',u)$$
