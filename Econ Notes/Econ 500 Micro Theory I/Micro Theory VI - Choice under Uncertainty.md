---
aliases:
creation date: Friday, October 7th 2022, 1:19 pm
date updated: Friday, October 7th 2022, 1:44 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Micro Theory VI - Choice under Uncertainty]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## Von Neumann-Morgenstern Expected Utility

### Setup

The process of making choices under uncertainty requires a somewhat different setup. 

First, we can establish primitives. 
- Let $X$ be a set of <font color=gree>consequences</font>. Finite, for convenience. 
- Let $L$ be a lottery, a mapping $L:X \to [0,1]$ that describes a probability density across $X$ such that $\sum_X p(x) =1$. 
	- <font color=#F7B801>This is pdf of an X valued random variable</font>
	- One can take scalar multiples of a lottery by saying that for all $x \in X$, $cL(x) = L(cx)$. 

#### VNM Axioms (Preferences)
 
 Define $\succsim$ as a preference relation on $L \times L$. This preference relation has the following properties
 1) Complete and Transitive
 2) Independent: for any lotteries $p,q,r$ and constant $\alpha \in (0,1)$, we have

$$ p \succsim q \implies \alpha p + (1-\alpha)r \succsim \alpha q + (1-\alpha)r$$
3) Continuity: If $p,q,r$ are lotteries, and $p \succ q \succ r$, then there exists $\alpha \in (0,1)$ such that 
$$q \sim \alpha p + (1-\alpha) r$$
As with our previous continuity axiom, we can describe this as saying that upper countour sets $\{q: p \succsim q\}$ and lower contour sets $\{ q: q \succsim p\}$ are closed

### Theorem

Some preferences $\succsim$ fulfil the three axioms: ie. complete & transitive, independent, continuity IFF there is some utility function over consequences, $u: X \to \R$, such that 
$$ p \succsim q \iff \sum_{x \in X} u(x)p(x) \geq \sum_{x \in X} u(x)q(x)$$
This $u$ is unique up to positive affine transformations (ie. linear transformations without the requirement $f(0) = 0$). 

#### Proof
A nice constructive proof. 

For convenience, $X$ is finite. 
Then $X$ has a best element $\overline x$ and a worst element $\underline x$: 
$$ x \in X \implies x \succsim \underline x \land \overline x \succsim x $$
Let's define $u(\overline x)$ as $1$ and $u(\underline x)$ as $0$. 

```ad-note
title: Lemma 1
```
Suppose $\alpha, \beta \in [0,1]$. Then
$$ \alpha \overline x + (1-\alpha) \underline x \succsim \beta \overline x + (1-\beta) \underline x$$
if and only if
$$ \alpha > \beta$$
**Proof of Lemma 1**: Suppose first $\alpha > \beta$. Then: 
$$\begin{align}
\alpha \overline x + (1-\alpha)\underline x&= 
\beta \overline x + (\alpha - \beta)\overline x + (1-\alpha) \underline x \\
&= [(\alpha - \beta)\overline x] + \beta \overline x + (1-\alpha) \underline x \\
&\succ [(\alpha - \beta)\overline x] + \descbox{r}{\beta \underline x} + (1-\alpha) \underline x 
\end{align}$$
