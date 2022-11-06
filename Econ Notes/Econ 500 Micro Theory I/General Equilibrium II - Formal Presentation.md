---
aliases:
- "Pareto Optimality"
- "Pareto Criterion"
- "First Welfare Theorem"
creation date: Sunday, November 6th 2022, 10:46 am
date updated: Sunday, November 6th 2022, 1:45 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[General Equilibrium II - Formal Presentation]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

[[Econ 500 Micro Theory Index]]

## Setup

We're interested in formally presenting and demonstrating many of the conclusions drawn from the Edgeworth Box framework. In particular, we're going to introduce more than two consumers, and we will also introduce firms and profit-maximization. 

1) There are $I$ consumers, $J$ firms, and $L$ commodities, all positive. 
2) Each consumer has a consumption set $X_i$ and a preference relation $\succsim_i$ defined on $X_i \times X_i$. Assume $X_i$ is closed, and bounded below ($\forall i \;; \exists \; r_i \in \R^L$ s.t. $X_i \subseteq r_i + \R^L_+$. While we will generally assume LNS, we'll bring it up usually. Specifically, we do not assume convex preferences. 
3) Each firm has some prouction set $Y_j$ such that $Y_j \subseteq \R^L_-$; there's no free lunch, $Y \cap \R^L_+ = \{0\}$, and free disposal. Can also write: $y \in Y \land -y \in Y \iff y = 0$. $Y$ is convex. 
	1) There's a total production set $Y$ which we write $Y = \sum_j Y_j$: this just means every firm is producing something from their set. Formally $y\in Y \iff \exists\,c \in \R^J \text{ s.t. } c'(y_1, \ldots, y_j) = y$. 
4) There is an aggregate endowment $\bar\omega$ There is some $x \in X_1 \times X_2 \times \ldots$ such that $x < \bar\omega$. 
5) An allocation is some $x,y$ set of decisions by firms and consumers. 
6) Let $a$ be an allocation in $\R^{(I + J)L}$. Then $a$ is <font color=gree>feasible</font> if it contains $x, y \in X, Y$ such that $\sum_i x_i = \sum_j y_j + \bar\omega$. The total consumption is no more than that which is endowed + that which is produced. The feasible set $A$ is nonempty and closed.

For now there is no private ownership - no distribution of firm profit is specified, nor ownership of endowments. 

## Important Concepts

### Pareto-Optimality

An allocation $x,y$ is Pareto-optimal if
1) it is feasible
2) $\not\exists\; x', y'\text{ s.t. } x' \succsim_i x$ for all $i$, $x' \succ_j x$ for some $j$, and $x', y' \in A$. In other words, there's some other feasible allocation that makes nobody worse off and someone better off. 

It's worth noting that this is a really weak condition. $x_1 = \bar \omega$ is PO; someone has all the stuff. 

### Walrasian Equilibrium

Now we can introduce a notion of income and ownership. 
- Individuals have endowments $\omega_i$ such that $\sum \omega_i = \bar\omega$. 
- Firms have ownerships $\theta_{ij}$ : $\sum_j \theta_{ij} = 1$. 
Suppose some prices $p \in \R^L$. Then an individual's income is $w_i = p \omega_i + \sum_j \theta_{ij}py_j$. 

Then we will say that an allocation $x^*, y^* \in A$, and some prices $p$, are a Walrasian Equilibrium if: 
1) $\forall j\;, \; \forall y_j \in Y_j, py_j^* \geq py_j$. Firms are profit maximizing. 
2) $\forall _i$ $x_i \in X_i$: $x_i^* \succ_i x_i \implies px_i > w_i$. Consumers are utility maximizing given their budget. 

### Price Equilibrium with Transfers

For this case we don't actually care who owns what. We just care about some $w_i$ such that $\sum w_i = p \bar\omega + \sum_j py_j$. That is, there's some division of aggregate wealth. 

Some allocation $x^*, y^* \in A$ and prices $p \in \R^L$ is a <font color=gree>price equilibrium with transfers</font> if 
1) $\forall j\;, \; \forall y_j \in Y_j, py_j^* \geq py_j$; the profit maximization condition. It might be convenient to write this as $p(y_j^* - y_j) \geq 0 \; \forall y_j \in Y_j$. 
2) $\forall _i$ $x_i \in X_i$: $x_i^* \succ_i x_i \implies px_i > w_i$. Consumers are utility maximizing given their budget. 

The Walrasian Equilibrium is a special case of the PEWT where transfers are $0$. 

## First Welfare Theorem

Assume preferences are locally nonsatiated. Then if $x^*, y^*$ is a price equilibrium with transfers, it is Pareto Optimal. 


### Proof

Assume for a contradiction that there's a Pareto-improving bundle. Then there is some $x, y \in A$ such that $x_i \succsim x_i^*$ for everyone and $x_j \succ x^*_j$ for some $j$. Then by the utility maximization condition, $px_j > px_j^*$. 

Now consider the LNS condition. We know $x \succ x^* \implies px> px^*$. Suppose $x' \succsim x$ but $px' < px$. The latter implies that for some $r>0$ there is some ball $B_r$ around $x'$ such that $x_r \in B_r \implies px_r < px$. But LNS tells us that there is some $x'_r \in B_r$ such that $x'_r \succ x'$; and by transitivity, $x'_r \succ x$; but $px'_r < px$, contradicting utility maximization. So by LNS we have that $x_i \succsim x_i^* \implies px_i \geq px_i^*$. 

Then at this new bundle we can write the total social wealth as: 

$$\begin{align}
\sum w_i &= \sum_i p_i x_i^*\\
&= px_j^* + \sum_{i \neq j} px_i^* \\
&< px_j + \sum_{i \neq j} px_i\\
p \bar\omega + \sum_j py_j &< px_j + \sum_{i \neq j} px_i
\end{align}$$

Thus this is not a feasible allocation. 


## Second Welfare Theorem

The FWT tells us that WE/PEWTs are Pareto-optimal. We want to show that all pareto optimal points are WE. This unfortunately is not true. So we'll want a weaker idea of equilibrium, quasiequilibrium. Then we can say a) all pareto optimal points are QE and that under certain conditions, a PQWT is a PEWT. 

We will also need to introduce the convex preference assumption. 

### Quasiequilibrium

#### Motivation

#status/section/🚧 

#### Definition

So we will want to relax the notion of equilibrium - specifically, the part where consumers are utility-maximizing. Instead we will have the condition that, for some $x^*$, there is nothing better that is cheaper: $x \succ x^* \implies px < px^*$. 

### Theorem

Suppose that $X_i, Y_j$ convex, and $\succsim_i$ convex. Then, for every feasible Pareto-optimal allocation, there exist some post-transfer wealths $w$ such that $x^*, y^*$ is a PQWT. 

### Proof

We're going to do the separating hyperplane theorem. First we have to construct the things to separate. $Y + \bar\omega$ is convex since it is the 'sum' of convex sets. For all consumers, let $V_i = \{ x_i \in X_i| x_i \succ_i x_i^*\}$. Now, suppose $x, x' \in V_i$, and let $x \succsim x'$. Then let $x'' = \alpha x + (1-\alpha)x'$. The convexity of $X$ tells us $x'' \in X_i$; the convexity of $\succsim_i$ means that $x \succsim x'' \succsim x$. So $x'' \succsim x$, $x \in V_i$, so $x \succ x_i^*$ and thus $x'' \succsim x_i^*$. So $V_i$ is convex, and the aggregate $V = \sum_iV_i$ is convex. 

The sets $Y + \bar \omega$ and $V$ are disjoint: Let $x \in V$. Then $x \succ x^*$. Suppose they are not disjoint, so $x \in Y+\bar\omega$. Then since $x \succ x^*$, we contradict pareto optimality. 

So we can use the separating hyperplane theorem. There is some $p \neq 0$ defining the plane $pz = r$ such that $v \in V \implies pv \geq r$, and $y \in Y + \bar\omega \implies py \leq r$. 

If $x_i \succsim_i x_i^*$ for all $i$ then $p(\sum_i x_i) \geq r$: For every $i$ and all $r>0$ there is a ball $B_{ri}$ around $x_i$ such that $\exists x_{ri} \in B_{ri}$ and $x_{ri} \succ x_i$. Since $x_i \succsim x_i^*$, $x_{ri} \succ x_i^*$. So $x_{ri}$ is in $V_i$; so $\sum_i x_{ri} \in V$. Then $p\sum_i x_{ri} \geq r$. But $x_{ri} = x_i + \epsilon$: so as $\epsilon \to 0$, $x_{ri} \to x_i$, and, since $\{z|z\geq r\}$ is closed, this means that $p\sum_i x_i \geq r$. 

Since this is true in aggregate, for every $i$ $x_i \succ_i x_i^* \implies px_i \geq px_i^*$. 
