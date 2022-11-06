---
aliases:
- "Pareto Optimality"
- "Pareto Criterion"
- "First Welfare Theorem"
creation date: Sunday, November 6th 2022, 10:46 am
date updated: Sunday, November 6th 2022, 11:05 am

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
