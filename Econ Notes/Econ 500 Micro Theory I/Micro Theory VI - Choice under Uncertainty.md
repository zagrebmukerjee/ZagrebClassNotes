---
aliases:
creation date: 2022-10-07 13:19
date updated: 2022-10-07 13:19

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
As with our previous continuity axiom, we can describe this as saying that upper countour sets $\{q: p \succsim q\}$ and  lower contour sets $\{ q: q \succsim p\}$ are closed

### Theorem

Some preferences $\succsim$ fulfil the three axioms: ie. complete & transitive, independent, continuity IFF there is some $u: X \to \R$