---
aliases:
creation date: Saturday, April 15th 2023, 4:00 pm
date updated: Saturday, April 15th 2023, 4:26 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Mechanism Design 501 IV - Bilateral Trade]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

We're moving now from a setting where one party has private information - the buyers in an auction, say - to one where both parties do. Are there circumstances under which trade can still take place? A rather depressing result, the Myerson-Satterthwaite Theorem, tells us that it's rather hard. 

## Setup
Suppose there is a boyer and a seller. The seller can produce 1 item at (private) cost $\theta_s$; the buyer, if consuming that item, will get utility $\theta_b$. 
The feasible allocations can be described as $X = \{q, t\}$ where $q = Pr($trade$)$ and $t$ is the price paid, with $\sum t_i \geq 0$ (no outside funding). The buyer utility is $q(\theta_b - t_b)$, and the seller utility is $q(t_s - \theta_s)$. $\theta_i$ has distribution function $F_i$ with support $[\underline \theta_i, \overline \theta_i]$, with $\Theta = \Theta_b \times \Theta_s$. 

A direct mechanism is a pair of functions, $q: \Theta \to [0,1]$ and $t:\Theta \to \R^2$. $q$ is decision efficient if $q = 1$ when $\theta_b >\theta_s$ and $0$ otherwise. Budget balance in this case just means $t_b = -t_s$: no frictions. As shown in [[Mechanism Design 501 III - Generalization, Efficient Mechanisms]], these two conditions are equivalent to ex-post Pareto efficiency. 

Define an interim epected utility, with $Q_i = \theta_i E[q(x_i, \theta_j)] - E_i[t_i(x_i, \theta_j)]$, and $T_i = E[t_i(x_i, \theta_j)]$. 

## Myerson-Satterthwaite Theorem

The following are equivalent: 
1) Either $\overline \theta_S \leq \underline \theta_B$ or $\underline \theta_S \geq \overline \theta_B$
2) There exists a mechanism with $IR$, $IC$, $DE$ and $BB$. 

In other words, a mechanism satisfies the 4 desiderata if and only if we're in the degenerate case where $\overline \theta_S \leq \underline \theta_B$ or $\underline \theta_S \geq \overline \theta_B$; trade will never or always be optimal. 
The intuition is that in nondegenerate cases, there is simply too much information rent to be covered by the gains from trade. 

### Proof
$\impliedby$ is easy. If in the degenerate case, a mechanism exists that satisfies the 4 properties - just let $q=1$ or $0$ always. and pick some $t$ in $[\overline \theta_s, \underline \theta_B]$. 
For $\implies$: 
First recall the [[Mechanism Design 501 I - Motivation, Screening Problem#Myerson 1981 Lemma and Envelope Formula|Myerson 1981 Lemma]]. A mechanism is IC if and only if $q$ is increasing in $\theta$ and $U(\theta_i) = U(\underline \theta) + \int_{\underline \theta}^{\theta_i} q(x)dx$. 

Suppose a contradiction, ie. $\Theta_B \cap \Theta_S \neq \emptyset$ but there is a mechanism with the $4$ properties. Then we will compute two expressions for the ex-ante social welfare, from budget balance and from IC, and show them to be contradictory. 

1) Let $W$ be ex ante social welfare. $$\begin{align}
W &= E[U_B(\theta_B) + U_S(\theta_S)]\\
&= E[\theta_BQ_B(\theta_B) - T_B(\theta_B) + T_S(\theta_S) -  \theta_S Q_S(\theta_S)]\\
&= E[\theta_BQ_B(\theta_B) -  \theta_S Q_S(\theta_S)] + E[T_S(\theta_S)- T_B(\theta_B) ]\\
&=  E[\theta_BQ_B(\theta_B) -  \theta_S Q_S(\theta_S)] \\
\end{align}$$
using the law of 