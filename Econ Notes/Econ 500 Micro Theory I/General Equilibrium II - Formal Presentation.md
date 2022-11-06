---
aliases:
- "Pareto Optimality"
- "Pareto Criterion"
- "First Welfare Theorem"
creation date: Sunday, November 6th 2022, 10:46 am
date updated: Sunday, November 6th 2022, 11:27 am

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
2) Each consumer has a consumption set $X_i$ and a preference relation $\succsim_i$ defined on $X_i \times X_i$. Assume $X_i$ is closed, and bounded below ($\forall i \;; \exists \; r_i \in \R^L$ s.t. $X_i \subseteq r_i + \R^L_+$. While we will generally assume LNS, we'll bring it up usually.  
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
