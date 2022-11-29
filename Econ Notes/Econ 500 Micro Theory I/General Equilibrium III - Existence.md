---
aliases:
creation date: Saturday, November 26th 2022, 3:32 pm
date updated: Monday, November 28th 2022, 2:59 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[General Equilibrium III - Existence]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Motivation and Setup

We want to be able to understand the conditions under which a Walrasian Equilibrium exists. Why? Well, if these conditions are totally crazy, it may tell us that we don't have that good of an equilibrium concept. 

First, recall the definition: 

![[General Equilibrium II - Formal Presentation and Welfare Theorems#Walrasian Equilibrium]]

The overall approach will be:
- describing the WE as the solution of a system of equations;
- establishing properties of equilibria based on this description, and;
- using [[Fixed Point Theorems - Brouwer and Kakutani|fixed point results]] to establish the existence of equilibria. 

### Excess Demand

First suppose the simple case of a pure exchange economy: $J = 1$, $y_1 = -\R_+^L$ (there is only one firm and all it does is free disposal).

Restrict the consumption sets $X_i$ to $\R^L_+$ and assume preferences are continuous, [[Micro Theory IIIa - Concave, Convex, Quasi|convex (econ)]], and locally nonsatiated. Assume that $\sum_i \omega_i >>0$; that is, there's some of every good. 

Then we can rewrite the WE conditions as: 
1) $y_1^* \leq 0$, $p y_i^* = 0$, and $p \geq 0$. 
	1) The first follows from the free disposal firm; the third, from market clearance (which rules out infinite disposal of something); and the second from maximization conditional on $p \geq 0$. 
2) $x_i^* = x_i(p, p\omega_i)$ for all $i$ (restating equilibrium consumption as [[Micro Theory II - Utility Maximization|Marshallian demand]])
3) $\sum_i x_i^* - \sum_i \omega_i = y_1^*$

This lets us establish a new condition for WE:

In a pure exchange economy, $p \geq 0$ is a WE price vector if and only if: 

$$ \sum_i (x_i(p, p\omega_i) - \omega_i) \leq 0$$

Intuitively, this means that no more can be consumed than is endowed. It follows from the WE conditions. In the other direction: suppose the statement is true, and let $y_1^*$ be $\sum_i (x_i(p, p\omega_i) - \omega_i)$, and $x_i^* = x(p, p\omega_i)$, Then condition 2) is met by definition, as is condition 3. Condition 1 follows from the assumptions. 

Note:
$$\begin{align}
py_1^* &= p\left[ \sum_i (x_i(p, p\omega_i) - \omega_i)\right]\\
&=\sum_i \left[px_i(p, p\omega_i) - p\omega_i\right]\\
&= 0
\end{align}$$
which follows from LNS/Walras' Law. 


We can call $x_i(p, p\omega_i) - \omega_i$ the <font color=gree>excess demand</font> of consumer $i$, written $z_i(p)$; the aggregate excess demand is an $l-$ vector, $z(p)$.

Now we can state the above condition more simply: $p \geq 0$ is a WE price vector if and only if $z(p) \leq 0$. 

### Properties of Excess Demand

Now, suppose preferences are strongly monotone. Then: 
1) $z(p)$ is continuous. 
2) $z(p)$ is homogeneous of deg 0. 
3) $pz(p) = 0$ for any $p$ (Walras' Law)
4) For any $p$, there is an $s > 0$ such that $z_\l(p) > -s$ for all $\l$ 
	1) Since demand is nonnegative, net supply can be no greater than endowment
5) Suppose $p_n \to p$, $p \neq 0$, but for some $\l$ $p_\l = 0$. Then $\max _{\l \in L} z_\_l(p_n) \to \infty$
	1) there's some consumer with positive weatlh. Strong monotonicity means that as $p_\l$ to $0$, $z_l(p)$ for that guy goes to infinity.


```ad-note
title:
Walras' law gives us another equation in this system: that means, if all but one price satisfies our excess demand criterion, the last must also (i.e. we only have to check that all markets but one clear). 

```

This can be extended to a general production case with 'production inclusive excess demand' functions. #status/section/🚧 

## Existence

The overall approach is to set up for using [[Fixed Point Theorems - Brouwer and Kakutani|Kakutani's Fixed Point Theorem]]. This means
1) Create a correspondence from prices into itself that - loosely - moves towards W. equilibrium
2) Demonstrate that a fixed point of this correspondence is an equilibrium
3) Show that this correspondence meets the Kakutani conditions: convex-valued and [[Micro Theory IIIb - Hemicontinuity|upper hemicontinuous]]. 
4) Use KFPT to demonstrate equilibrium. 

### Conditions

Need:
- $z(p)$ defined on all $p \in \R_+^L$
- meeting conditions above (cont, homogeneous, Walras' Law, bounded below, unbounded with $p \to 0$)
ie. $\sum_i \omega_i >> 0$, and preferences are continuous, SCX, strongly monotone.

Then for some $p$, $z(p) = 0$, meaning a WE exists.

### Setup

First create a price simplex $\Delta$ denoting all relative levels of prices. For convenience we can make this the unit simplex: 

$$ \Delta = \bigg\{ p \in \R^L_+: \sum_\l p = 1 \bigg\}$$

So in $\R^2$ this is a line segment with ends $(0,1)$ and $(1,0)$. 

We'll want to separately consider the interior of the simplex and its boundary: $z()$ is not well defined when some $p = 0$. <font color=#F7B801>why</font>

### Step 1: Correspondence

First we make a correspondence $f:\Delta \to \Delta$. Proceed in two cases: 

#### Case 1: $p >> 0$
$$ f(p) = \{ q \in \Delta: z(p) \cdot q \geq z(p) \cdot q' \hspace{10pt} \forall \; q' \in \Delta \}$$
Given a price $p$, there's some excess demand for all commodities $z(p)$. An element of $q$ is a price which maximizes the cost of $z(p)$ - intuitively, we are looking for equilibrium by making the excess demand more expensive. 

If $z_i(p) < \max_{\l \in L} z_\l(p)$ then $q \in f(p) \implies q_\l = 0$. So set all prices to $0$ except for those commodities most excess-demanded. Recalling that we are in relative prices space, this makes sense (if it were not true we could maximize more by putting more 'weight' on the more-demanded good). 

Walras' law tells us that $pz(p) = 0$ for all $p$. So if $p >>0$ and $z(p) \neq 0$, then we have some commodities $a$ and $b$ such that $z_a(p) > 0$ and $z_b(p) < 0$. Therefore, commodity $b$ has $q \in f(p) \implies q_b = 0$. This means that $q$ is on the boundary of the simplex. 

If $z(p) = 0$, then any price $q$ 'maximizes',, so $f(p) = \Delta$. 

#### Case 2: $\exists \l: p_\l = 0$
In this case, the correspondence sets to $0$ all nonzero prices. 
$$f(p) = \{ q \in \Delta: pq = 0\}$$
In particular, $q \in f(p), p_\l > 0 \implies q_\l = 0$. Because we have some element of $p$ that is $0$, we can still have $q$ in the simplex (in the case where just one $p$ is $0$, $q$ will be a vertex). Also there are no boundary fixed points of $f()$. 


### Step 2: Fixed Point = Equilibrium

Suppose some interior point $p^* \in \Delta: p^* \in f(p^*)$. Then $z(p^*)\cdot p^* \geq z(p^* )\cdot q$ for any $q \in \Delta$. Recall that if $z(p) > 0$, then $f(p)$ is on the boundary of the simplex, and so it can't be a fixed point. So we must have $z(p) = 0$, and thus an equilibrium. 


### Step 3: Kakutani Conditions

#### Convex-Valued
Let $\Delta_L$ be the simplex of prices with $L$ vertices. 

If we are in the interior and $z(p) = 0$ then $f(p) = \Delta$ and is convex valued because it's a simplex. 
If $z(p) \neq 0$, or we are on the boundary, then let $q, q' \in f(p)$ with $q \neq q'$, and $q, q'$ in the boundary of $\Delta$. 
If no such pair exists then $f(p)$ is trivially convex. 
We know that $q z(p) = q' z(p)$. Let $q'' = \lambda q + (1-\lambda)q'$. 

In the boundary $z_\l(p) \notin \max_{i \in L} z_i(p)$ if and only if $q_\l = q'_\l = q''_\l = 0$. The first direction is demonstrated in the book. To see the inverse: we know $z(p) \neq 0$. Let $z_\l(p) \in \max \ldots$; then (as argued in the book also) $z_\l(p) > 0$, Let $r = q$ except with $r_\l>0$, then $rz(p) > qz(p)$, a contradiction. 

But this means that if $q_\l \neq 0$ then $z_\l(p) \in \max \ldots$, and so $q'_\l, q''_\l \neq 0$. And since $q, q', q'' \in \Delta$, that means that the $q$s are in some $\Delta_{L -k}$, a face of the simplex: $\sum_{\l:z_\l(p) \in \max \ldots} q_\l, q'_\l, q''_\l = 1$ . So they are convex combinations of one another. 

#### UHC

Let $p_n \to p$, $q_n \in f(p_n)$, $q_n \to q$. Need only to demonstrate closed graph since we know compact-valuedness

If $p$ is in the interior, then pass to a subsequence such that $p_n >>0$. So $q_n >> 0$. Then we can take $q_nz(p_n) > q'z(p_n)$ and say it holds in the limit. So $q \in f(p)$; the graph is closed. 

If $p$ is in the boundary, choose $\l$ with $p_\l >0$, then for some subsequence $p_{n, \l} > 0$. So $q_{n, \l} = 0$ if $p_n$ is on the boundary. If not, then we know from the last boundary condition that given sufficiently large $n$, $z_\l(p_n) \notin \max_{i \in L} z_i(p)$. So $q_{n, l} = 0$ by construction. Therefore, $q_\l = 0$, and so $pq = 0$ and $q \in f(p)$. 

### Step 4

Apply Kakutani. Boom. 
