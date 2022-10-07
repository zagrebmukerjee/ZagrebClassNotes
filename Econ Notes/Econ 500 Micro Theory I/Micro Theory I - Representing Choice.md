---
aliases:
creation date: Thursday, September 1st 2022, 5:23 pm
date updated: Wednesday, September 14th 2022, 1:59 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#topics/econ/theory/micro'
---

# [[Micro Theory I - Representing Choice]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 500 Micro Theory Index]]

## 3 Modes of Choice Representation

We will discuss 3 different representations of choices. 
- Preferences: Most primitive. Good axiomatic foundation
- Choice functions: Map most clearly to what's observed
- Utility functions: analytically very useful. 

We'll demonstrate that these are essentially equivalent. 

### Choice Functions

Choice functions and preferences have to have 2 properties. Loosely:
1) "enough information"
2) "no contradictory information"

Together these are often called 'rational'. "Consistent" might be preferable, having less normative content. 

Let $X$ be some set of alternatives. $C()$ is a choice function such that $C(A)$ is a collection of alternatives chosen from $A \subseteq X$. If $P(X)$ is the power set of $X$, $C: P(X) \to P(X)$ s.t. $C(A) \subseteq A$. 

Two conditions. 

#### Finite Non-Emptiness
- "Enough information":. Given non-empty $A$ and finite $A$, $C(A) \neq \emptyset$. 
- Why must $A$ be finite? Consider $C(A) = \max A$; let $A = [0,1)$; oh no... 

#### Coherence
- Let $x,y$ be in $S \cap T$. Suppose: 
	- $x \in C(S)$.
	- $y \notin C(S)$. 
  Then $y \notin C(T)$. We'll later discuss how this is the same as transitivity. 
- The intuition here is: In $S$, I had the choice of $y$, I chose $x$ over $y$. Therefore, when looking at $T$: both $x$ and $y$ are choices. I may not choose $x$ because there might be something in $T \cap S^c$ that's better than $x$. But in all scenarios where I could be choosing $y$ from $T$, I'd rather choose $x$. 


### Preferences

Preference is some subset of the set of pairs - a description of which is 'preferred'. We write $x \succsim y$; "$x$ is at least as good as $y$."  

From this, we can create $x \succ y$ - $x$ is strictly better than $y$, which is true when $x \succsim y$ but $\neg(y \succsim x)$. 

I can also make $x \sim y$, or $x$ is indifferent to $y$, which is the case when both $x \succsim y$ and $y \succsim x$. 

I once more have two conditions: 

- Completeness: For every $x,y$ either $x \succsim y$, $y \succsim x$, or both. 
- Transitivity: If $x \succsim y$ and $y \succsim z$, then $x \succsim z$. 


## Equivalences
We will now produce four results showing these things are equivalent. 

### The Easy Ones

Suppose utility function $u(x)$. Define $x \succsim y \iff u(x) \geq u(y)$; and define $C(A) - \underset{x \in A}{\arg \max} \; u(x)$. 
Given some complete and transitive preferences, define $C(A) = \{ x \in A : y \in A \implies x \succsim y\}$. 

Given these definitions, we can write: 

#### Proposition 1
1) $u$ induces a coherent, FNE choice function $C$.
2) $u$ creates complete, transitive preferences, which
3) create a coherent, FNE choice function $C'$
4) $C'(A) = C(A)$ $\forall$ $A \subseteq X$. 
5) If $C$ is FNE/coherent then $\exists$ $\succsim_c$ generating $C'$ such that, if $C(A) \neq \emptyset$ (case of infinite $A$), $C(A) = C'(A)$. 

#### Proof of Proposition 1

If $x \in C(\{x,y\})$, then write $x \succsim_C y$. 
- By FNE, we can say this exists for every pair $x,y$. So it is complete. 
- For transitivity: Suppose $x \succsim_c y$ and $y \succsim_c z$. Then a) $x \in C(\{x,y\})$ and b) $y \in C(\{y,z\})$. Consider now $R = C(\{x,y,z\})$. From applying coherence on b) we know that $z \notin R$. From coherence and a), we know that $y \notin R$. So by FNE it follows that $x\in R$. Now, we can use coherence once more to say that since $\{ x,z\}$ is a subset of $\{x,y,z\}$, $x$ must be in $C(\{x,z\})$. So it follows that $x \succsim_C z$. 


Then create $C'$, with $C'(A) = B$, defined as: $x \in B \iff (y \in A \implies x \succsim y)$. We now can show $C(A) \subseteq C'(A)$ and vice versa. 
- Suppose $x \in C(A)$. Then $\forall \; y \in A$, for each pair $\{x,y\}$, we know that $x \in C(\{x,y\})$ by coherence. So then $x \succsim_C y$, and thus $C(A) \subseteq C'(A)$. 
- Now, choose $A$ and $x \in C'(A)$. Then we know that $\forall \; y \in A$, $x \succsim_C y$. Choose some $y \in C(A)$ (by nonempty). By definition of $C'$, $x \succsim_C y$. So $x \in C(\{x,y\})$. Since $x$ is chosen from $\{x,y\}$, a subset of $A$, and since $y$ is chosen from $A$, $x \in C(A)$. So $C'(A) \subseteq C(A)$. 

## Representation Theorems

OK. But what about utility functions? 

One direction is straightforward: turning utility functions into our desiderata. The other one is sufficiently complex to merit the label of "representation theorems". But it's important to pin this down, because we'll want to use utility functions a lot, and we want them to have very solid foundations. In particular, we want to do this in an infinite choice space, which makes things more complex. 

```ad-note
title: Finite Representation Theorem

Suppose $X$  finite, and $C()$ finitely non-empty and coherent. Then there is a utility function:

$$
\begin{aligned}
x_1 &= C(X)\\
x_2 &= C(x \in X: x \notin \{ x_1\}) \\
\vdots & \\
x_k &= C(x \in X: x \notin \{ x_1, x_2, \ldots x_{k-1}\}) \\
\end{aligned}
$$

Then let $U(x) = k$ if $x \in x_1$, $k-1$ if $x \in x_2$, and so on. 

```



### Conditions

Let's say $\R^2$ is our consumption space. We're working with preferences that are complete, transitive, but also continuous and weakly monotonic. 

#### Continuity
We add the condition that they are continuous: i.e. $\forall x \; \{ y \in X: y \succsim x \}$ is a closed set, as is $\{ y \in X: x \succsim y\}$. 

In other words, there are upper and lower contour sets of $x$: all the bundles at least as good as $x$, and the bundles than which $x$ is at least as good. These are closed sets - intuitively, that means they contain their boundaries (which are indifference curves). 

Continuity is sometimes called a 'technical' assumption, in that we just use it for math simplification. Though people sometimes say 'this is a technical condition' to mean 'this is useful but I don't understand it'. So watch out for that. It can mean: I need it for math and it's either empirically contentless, or meaningless in finite land. 

An example of noncontinuous preferences: lexicographic $\succsim$. If $x \succ y$, then either $x_1 > y_1$, or $x_1 = y_1$ and $x_2 > y_2$, or so on. This is noncontinuous. Consider the 2 dimensional case. Some bundle $x_1$ is preferred to all sets with $x_1 > y_1$. But also all sets with $x_1 = y_1$ and $x_2 > y_2$. In other words, the set $y : x \succsim y$ is all points to the right of $x$ and also all the points directly below $x$, but not the points directly above. So the point $x_1, x_2 + 1$ is preferable to $x$, but it is a limit point of $y: x \succsim y$. 

In fact, there exists no function representing lexicographic preferences. 


#status/section/🚧 
```ad-note
title: Lexicographic Preference Cannot be Represented 


```

So continuity is not 100% technical. But we do want it. 

#### Monotonicity

This one is simple. Strong monotonicity is that $x \geq y \implies x \succ y$. Weak monotonicity is that $x > y \implies x \succ y$. In this case, given vectors $x$ and $y$, $x \geq y$ means that 'every element of $x$ is at least equal to its corresponding element in $y$, and at least one is greater'; $x > y$ means that $\forall i \; x_i > y_i$. 

A weaker version of monotonicity is local nonsatiation: every neighborhood of every bundle $x$ contains $y$ such that $y \succ x$. Either of these will tell us that the maximizing bundle is on the budget frontier. Monotonicity is more convenient. 


### Statement and Proofs (Prop 3)

Suppose $\succsim$ are complete, transitive, continuous, weakly monotonic. Then there is some continuous utility representation for $\succsim$.

#### Construct $U()$

Pick any two allocations in the diagonal. By weak monotonicity, we can say one is preferred. Now we just have to map everything to something on the diagonal to which it's indifferent - i.e. drawing indifference curves. 

For a point on the diagonal, let $U(\alpha, \ldots \alpha) = \alpha$. 

For any $x$ off the diagonal, we know by continuity that $y \succsim x$ and $x \succsim y$ closed. This is an indifference curve. 
By monotonicity, there are $\alpha_1$ on the diagonal such that $\alpha_1 \succsim x$, and $\alpha_2 \in D: x \succsim \alpha_2$ (easy examples: more or less of everything). The union of these sets is $\R$. The intersection - $\alpha \in D: \alpha \sim x$ - exists fron the continuity above. By weak monotonicity, no points on the diagonal are indifferent to each other; which means that we can't have $\alpha_1$ and $\alpha_2$ both indifferent to $x$, since either $\alpha_1 \succ \alpha_2$ or vice versa. 

Call the single point on the diagonal that's indifferent to $x$ $\alpha_x = (\alpha_x, \alpha_x, \ldots)$. Then we can say $U(x) = U(\alpha_x) = \alpha_x$. 


#### $U$ Is Continuous
Suppose $x_n \to x$; we want to show that $U(x_n) \to U(x)$. By our construction that means $\alpha_{x_n} \to \alpha_{x}$. 

Suppose that's not true: i.e., there are $x_n$ converging to $x$, but for every $n$, $\alpha_{x_n} > \alpha_x + \gamma$. This implies, given the construction above, that the indifference curves for $\alpha_{x_n}$ are always strictly above $I(\alpha_x)$: by monotonicity, we can find $\alpha_{x_n} \succ \alpha_x + \gamma/2 \succ \alpha_x$, and by transitivity we can extend that result to an indifference curve. 

Draw a neighborhood around $\alpha_x$ of radius $\gamma$; this then contains no $x_n$ in it, a contradiction. 


#### $U$ Represents $\succsim$

We want to show that $x \succsim y$ if and only if $U(x) \geq U(y)$. 

Since $x \succsim y$, we know that $(\alpha_x, \ldots) \succsim (\alpha_y, \ldots)$, by transitivity. So, on the diagonal, $\alpha_x \succsim \alpha_y$. So $U(x) > U(y)$. 
In the other direction: if $U(x) > U(y)$, then $\alpha_x > \alpha_y$, so $x \succsim y$ by transitivity. 

Observe: 
- If $U(x)$ represents $\succsim$, then for strictly increasing $f$, so does $f(U(x))$. In other words a utility function is 'unique only up to strictly increasing transformations.' 

```ad-note
title: Takeaways from the Proof

- Continuity is _not_ a strictly technical assumption, but this proof relies upon it. 
- A utility function contains exactly as much information as the preference relation it represents; a complete ordering of $(x_1, \ldots)$. Nothing we did lets us say 'how much better is $x$ than $y$?
- Transitivity is what lets us draw indifference curves from the diagonal to all $\R^n$. Otherwise we would have a big mess with indifference correspondences. 
- The structure of $U$ implies both completeness and transitivity. 

```

## Choice, Utility, Revealed Preference

We can also represent choice functions with utility functions.

We know that choice functions correspond to preferences, and we've shown that preferences can be represented by utility functions. Why bother showing that choice functions are represented by a utility function? Well, when we [[#The Easy Ones#Proposition 1|argued]] that choice functions could generate preferences, we tacitly assumed that we could define choices over arbitrarily large sets. We don't need to require that to construct $U$ from $C$. 

### Weak Axiom of Revealed Preference (WARP)

Restating the coherence criterion: 

![[#Choice Functions#Coherence]]


Suppose prices $p$ and income/wealth $w$. Let $x(p,w)$ be the bundle that maximizes utility under $p,w$. Then if 
- $x(p,w) \neq x(p',w')$
- and $px(p', w') \leq w$
- Then $p' x(p,w) > w'$. 

Easiest to think of in the case when $x(p,w)$ is a singleton. If bundle $x(p',w')$ is also affordable under $p,w$, but my optimizer is $x(p,w) \neq x'$, then I know that $x(p,w)$ is not affordable under $p', w'$; otherwise, I would have chosen it instead of $x(p',w')$. 

In this case, I can say $x$ is 'revealed preferred' to $x'$: given the choice of both, I picked one. As one might suspect, this is the same criterion as coherence. Let $B_1 = \{x : px \leq w\}$ and $B_2 = \{ y: p'y \leq w'\}$. Let $S = B_1$ and $T = B_2$. The WARP conditions map to the coherence conditions:
- Choose $x$ as feasible under $B_1$, and then $x \in S$, $x$. Let $y \neq x$ be the maximizer under $B_2$, and $y \notin C(S)$.
- Suppose $y \in S \cap T$. This is the same as saying that $px(p', w') \leq w$. Then suppose $x$ is also in $S \cap T$, which means $p'x(p,w) > w'$. Then, by WARP, $x \notin C(S)$, or $x \neq x(p,w)$. 

This is simply a rearrangement of the coherence criteria as "at most $n-1$ of the following criteria can be true". 

### SARP, GARP, Afriat's Theorem

We can make WARP into a stronger form. Let $\succsim_{R^0}$ be 'revealed preferred to'. Then let $\succsim_R$ be the transitive closure of $\succsim_{R^0}$. Then SARP states that $x \succsim_R y$ means $\neg(y \succsim_R x)$. So counts 'indirectly revealed preferred to' as well. 


GARP is a broader form of the above. Create the relation 'revealed strictly preferred to', $py < w$, or $x \succ_{R^0} y$, with transirive closure $\succ_R$. Then, in some data $p^i, w^i, x^I$, GARP holds if there is no $x^i \succ_R x^i$. 

#### Afriat's Theorem

If some data $\{p_i, w_i, x_i\}$ satisfy GARP, then there is a continuous increasing concave utility function rationalizing these choices. 
