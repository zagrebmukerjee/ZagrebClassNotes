---
aliases:
- "Hicksian demand"
creation date: Friday, September 23rd 2022, 11:46 am
date updated: Saturday, November 26th 2022, 3:48 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#topics/econ/theory/micro'
---

# [[Micro Theory III - Demand, Duality and Decomposition]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Indirect Utility

### Definition
For any $p,w$, we can write demand functions $x(p,w)$, the solutions to the utility maximization problem. Define the <font color=gree>indirect utility</font> of $p,w$ to be 
$$ v(p,w) = u(x(p,w))$$
that is, the utility obtained when utility is maximized. 

It's clear that $v$ is homogeneous degree $0$, since $x$ is $HD0$. $v$ must be strictly increasing in $w$ and weakly decreasing in $p$, by the fact of optimization. 

### Quasiconcavity
We also know that the indirect utility function is [[Micro Theory IIIa - Concave, Convex, Quasi|quasiconvex]], meaning that $v(\lambda x + (1-\lambda)y) \leq \max \{ v(x), v(y) \}$. How? 
- ~~We could make an argument based on diminishing marginal returns. If eg. $p_1$ is very close to $0$ and $p_2$ is not, then maybe $x_2$ is much bigger than $x_1$ and I'd be better off if the prices are similar so that I could do some substitution. ~~
- This is misleading!! We don't require the QCV of $u$ to get QCX of $v$. 

Suppose that bundle $x$ is feasible under some convex combination of prices. Thus $(\lambda p + (1-\lambda) p') x \leq \lambda w + (1-\lambda)w'$. Distributing: $p\lambda x + (1-\lambda)p'x \leq \lambda w + (1-\lambda)w'$. Then I know that either $p \lambda x \leq \lambda w$ or $(1-\lambda)p'x \leq \lambda w'$; in other words, $x$ is feasible in one of the endpoints. So, by walras' law, one of the endpoints is weakly better than $x$. We didn't use quasiconcavity, though we did use monotonicity/local nonsatiation. 

### Marginal Utility of Income
Using $v$ we can recover the marginal utility of income. 

$$\begin{align}
\partial v(p,w)/\partial w &= \partial u(x(p,w))/\partial w \\
&= \sum_i \frac{\partial u}{\partial x_i} \frac{\partial x_i}{\partial w} \\
&= \lambda \sum_i p_i \frac{\partial x_i}{\partial w} \\
&= \lambda
\end{align}$$
🎉🎉🎉look who it is!!!! 🎉🎉🎉 Our friend the Lagrange multiplier returns at last

The last step there depends on some degree of trickery. When we are at an optimum we can say a lot of differential results go away. This is another [[Envelope Theorem]] style of result, that depends on our maximizing. Mathematically: we know that $px(p,w) = w$, we can differentiate by $w$, and get $\sum p_i (\partial x_i(p,w)/\partial w) = 1$. A (slightly illegal) way of writing this is $\sum pi \partial x_i(p,w) = \partial w$; if income goes up a bit, sum of expenditures can't go up by more. 


We can further make transformations: 

$$\begin{align}
\lambda &= \frac{\partial u}{\partial x_i} \frac{1}{p_i} \\
&= \frac{\partial u}{\partial x_i}\frac{\partial x_i(p,w)}{\partial w}\\
\end{align}$$
Here is another perspective on the marginal utility of income. The first step is our old friend the FOC; the second step is another bit of [[Envelope Theorem]] trickery. Specifically, I know that since I am optimizing, I must be indifferent between spending the marginal dollar on all goods. That means, with an incremental change in income, I will spread it over every good, which buys me a quantity equal to $1/p_i$. 


So how could I say that $\lambda = \sum_i\frac{\partial u}{\partial x_i} \frac{\partial x_i}{\partial w}$ but also that $\lambda = \frac{\partial u}{\partial x_i}\frac{\partial x_i}{\partial w}$ for just one good?? 

Once again, because we are maximizing. Also because the latter is in fact an $x(p,w)$. so notation is sloppy.

### Continuity
#### Continuity Proof 1
$v(p,w)$ is continuous. 

Proof: from PS2

Suppose $v(p,w)$ is the utility of $x(p,w)$ that maximizes the problem defined by $p,w$. Suppose continuous $u()$. Let $p_n \to p^*, w_n \to w^*$; then we want to show that $v(p_n, w_n) \to v(p^*, w^*)$. 

In the limit, $x(p_n, w_n)$ is feasible under $p^*, w^*$. I then know by the continuity of $u$ that $\lim u(x(p_n, w_n)) = \lim v(p_n, w_n) \leq v(p^*,w^*)$. Otherwise $v()$ would not be maximizing. 

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

Then, $v = \max_{x \in B(\theta)}: \Theta \to R$ is continuous in $\theta \in \Theta$.

$x(\theta)$, which is ${x: x \in \arg \max u}$, the arg-max correspondence (the demand correspondence) is compact-valued, closed, and [[Micro Theory IIIb - Hemicontinuity|upper hemicontinuous]]. 


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

Let $x'' \in x(p'', u)$ - exp minimizer under $p''$. Then $e(p'', u)$ is $p''x'' = \lambda p x'' + (1-\lambda)p'x''$. This cannot be greater nor less than both $px''$ and $p'x''$ - so $x''$ must be affordable under one of $p, p'$ and unaffordable under another. But we know that $u(x'') = u$ - so we cannot have both $e(p,u)$ and $e(p',u)$ be less than $e(p'', u)$, since I could then lower expenditure under $p''$ by switching to $x''$ while losing no utility. 

### Hicksian Demand

Our definition of $x(p,w)$ is the vector of consumption maximizing utility given $p,w$. This is the <font color=gree>Marshallian demand</font>, also known as Walrasian or uncompensated demand. 

Define a new demand function, $h(p,u)$:

$$ h(p,u) = \underset{u(x) \geq \bar u}{\arg \min} \; px$$
the expenditure minimizing demand for a utility level $\bar u$. In other words: suppose the prices $p$ were to change (increase) to $p'$. $h$ represents the consumption bundle meeting $\bar u$ while minimizing expenditure under the new price regime. This includes substituting away from more expensive goods/towards cheaper ones. 

This new demand is called the <font color=gree>Hicksian demand</font>, or compensated demand. It has a few immediate properties:
- $h$ is homogeneous of degree 0 in $p$ (i.e. all prices rise by the same factor -> no substitution)
- Convex preferences mean that $h$ is convex (i.e. the indifference curve still can have flat regions). 
- Strictly convex preferences mean that $h$ is SCX, and unique.


For the latter: we want to show that $h(p,u)$ is a convex set, given concave preferences. This is relatively straightforward. Consider convex combination $h'' = \lambda h + (1-\lambda) h'$ with $h, h' \in h(p, \bar u)$. By the concavity of preference it follows that $u$ is quasiconcave; then $u(h'') \geq u(h), u(h')$. So $h''$ is feasible under constraint $\bar u$. Given that $h, h' \in h(p, \bar u)$, then $ph = ph' = e(p,u)$, so $p h'' = \lambda ph + (1-\lambda) ph' = e(p, \bar u)$. 

Under strictly concave preferences, $h'' \neq h', h \implies u(h'') > u(h), u(h')$; but $ph'' = e(p, \bar u)$, i.e. $h''$ an expenditure-minimizing bundle. If $ph'' = ph$, and $u(h'') > u(h)$, then we can reduce $h''$ to $j$ so that $pj < ph$ and $u(j) = \bar u$. Thus $h$ cannot be an expenditure minimizing bundle unless $h = h''$. So under strictly convex preferences, the Hicksian is a function. 

#### Hicksian Duality
We can see the following: 
$$\begin{align}
h(p, \bar u) &= x(p, e(p, \bar u))\\
h(p, v(p, w)) &= x(p,w)\\
ph(e, \bar u) &= e(p,u)\\
u(x(p,w)) &= v(p,w)\\
\end{align}$$
with the last being repeated from before. 


## Demand-Related Results

Assume strictly convex preferences, i.e. SQCV utility, and $h$ and $x$ are functions. Then we can obtain a number of envelope-theorem results. 

### Shepard's Lemma

Start with the identity $ph(p,u) = e(p,u)$. Since it's an identity, we can implicitly differentiate with respect to some price $p_i$. 

$$\begin{align}
\frac{d}{dp_i}e(p,u) &= \frac{d}{dp_i}ph(p,u)\\
&= \left(\frac{d}{dp_i}\right)ph(p,u) + p\frac{d}{dp_i}h(p,u)\\
&= h_i(p,u)+ \begin{bmatrix} p_1 & p_2 & \ldots \end{bmatrix}\begin{bmatrix} dh_1/dp_i \\ dh_2/dp_i\\ \vdots \end{bmatrix} \\
&= h_i(p,u) + \sum_k^L p_k dh_k/dp_i\\
\end{align}$$
The sum $\sum p_k d h_k/dp_i$ is how much optimal expenditure changes on good $k$ with a marginal change in the price of $i$. But since Hicksian demand is compensated, the total expenditure change must be $0$ - thus this becomes 

$$ \frac{d}{dp_i}e(p,u) = h_i(p,u)$$
This is Shepard's lemma. 

#### Corollary
Assume $h$ is continuously differentiable. Differentiate Shepard's Lemma with respect to $p_j$:
$$\frac{\partial ^2 e(p,u)}{\partial p_i \partial p_j} = \frac{\partial h_i(p, u)}{\partial p_j}$$
We can make these into a matrix: 

$$ \begin{bmatrix} e_{11}(p,u) & \ldots & e_{1L}(p,u)\\
& \vdots & \\
e_{L1}(p,u) & \ldots & e_{LL}(p,u)

\end{bmatrix} = \begin{bmatrix} \partial h_1/\partial p_1 & \ldots & \partial h_1/\partial p_L \\
& \ldots & \\
\partial h_L/\partial p_1 & \ldots & \partial h_L/\partial p_L
\end{bmatrix}$$
This tells us a few things: 
1) The LHS is negative semidefinite by concavity of $e$. So RHS is negative semidefinite. 
2) Young's Theorem tells us that $e_{1L}(p,u) = e_{L1}(p,u)$. So $\partial h_i/\partial p_j$ = $\partial h_j/\partial p_i$. 
3) RHS $\times p$ is $0$ since $h$ is homogeneous degree $0$ in $p$. 

### Roy's Identity

Start with 

$$ v(p,w) = u(x(p,w))$$Differentiate with respect to $p_i$. 
$$\begin{align}
v(p,w) &= u(x(p,w))\\
\frac{\partial v(p,w)}{\partial p_i} &= \sum_{j=1}^L p_i\frac{\partial u(x(p,w))}{\partial x_j}\frac{\partial x_j(p,w)}{\partial p_i}\\
& \text{ but since the FOC tell us that }\frac{\partial u}{\partial x_j} = \lambda p_j, \\ 
\frac{\partial v(p,w)}{\partial p_i} &= \lambda \sum_{j=1}^L p_j\frac{\partial x_j(p,w)}{\partial p_i}\\
& \text{ and from the implication of Walras' law, } \sum_{j=1}^L p_j\frac{\partial x_j(p,w)}{\partial p_i} = -x_i(p, w)\\
\frac{\partial v(p,w)}{\partial p_i} &= -\lambda x_i(p,w)\\
\frac{\partial v(p,w)}{\partial p_i} &= -\frac{\partial v(p,w)}{\partial w} x_i(p,w)
\end{align}$$
or 
$$ x_i(p,w) = -\frac{\partial v/\partial p_i}{\partial v/\partial w}$$
