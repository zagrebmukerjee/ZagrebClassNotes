---
aliases:
creation date: Saturday, April 15th 2023, 4:00 pm
date updated: Saturday, April 15th 2023, 4:47 pm

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
Proof from Class

Suppose a contradiction, ie. $\Theta_B \cap \Theta_S \neq \emptyset$ but there is a mechanism with the $4$ properties. Then since $q$ is decision-efficient, there is a Groves mechanism with $h(\theta_{-i}) = k_i$, some constants, with the same $q$. By $IC$ lemma, agents' interim payoffs are pinned down as the same in the supposed mechanism and this Groves mechanism. So the transfers are the same, and the indirect utility is the same. 

The Groves transfers are, with $k_i > 0$ (for budget balance):

$$ t_S^G = \begin{cases} 
\theta_B - k_S &\text{ if } \theta_B > \theta_S\\
0 - k_S &\text{ otherwise}
\end{cases}$$
$$ t_B^G = \begin{cases} 
-\theta_S - k_B &\text{ if } \theta_B > \theta_S\\
0 - k_B &\text{ otherwise}
\end{cases}$$

This lets us write the interim utilities: 

$$U^G_B(\theta_B) = E[ \max \{ \theta_B - \theta_S, 0 \} | \theta_B] + k_B$$
$$U^G_S(\theta_S) = E[ \max \{ \theta_S - \theta_B, 0 \} | \theta_S] + k_S$$
So $E(U_B^G + U_S^G)$ is $2S + k_B + k_S$, where $S$ is the social surplus. But we also have $E[U_B^G + U_S^G] = S$. So $k_B + k_S = -S < 0$, but then this contradicts budget balance. 


%%Proof from Masaki slides - incomplete%%
%%First recall th[](Mechanism%20Design%20501%20I%20-%20Motivation,%20Screening%20Problem.md#Myerson%201981%20Lemma%20and%20Envelope%20Formula)]]. A mechanism is IC if and only if $q$ is increasing in $\theta$ and $U(\theta_i) = U(\underline \theta) + \int_{\underline \theta}^{\theta_i} q(x)dx$. 

Suppose a contradiction, ie. $\Theta_B \cap \Theta_S \neq \emptyset$ but there is a mechanism with the $4$ properties. Then we will compute two expressions for the ex-ante social welfare, from budget balance and from IC, and show them to be contradictory. 

1) Let $W$ be ex ante social welfare. $$\begin{align}
W &= E[U_B(\theta_B) + U_S(\theta_S)]\\
&= E[\theta_BQ_B(\theta_B) - T_B(\theta_B) + T_S(\theta_S) -  \theta_S Q_S(\theta_S)]\\
&= E[\theta_BQ_B(\theta_B) -  \theta_S Q_S(\theta_S)] + E[T_S(\theta_S)- T_B(\theta_B) ]\\
&=  E[(\theta_B-  \theta_S)q(\theta_b, \theta_s)] \\
\end{align}$$
So far so good. Now, 
2) Using the envelope formula. 
$$\begin{align}
U_B(\theta_B) &= U_B(\underline \theta_B) + \int_{\underline \theta_B}^{\theta_B} Q_B(x)dx\\
U_S(\theta_B) &= U_S(\underline \theta_S) + \int_{\underline \theta_S}^{\theta_S} Q_S(x)dx\\
W &= E[U_B(\theta_B) + U_S(\theta_S)]\\
&= E[U_B(\underline \theta_B) + U_S(\underline \theta_S) + \int \ldots ]\\
&= U_B(\underline \theta_B) + U_S(\underline \theta_S) + E[\int \ldots ]\\
\end{align}$$

$$\begin{align}
E\left[  \int_{\underline \theta_B}^{\theta_B} Q_B(x)dx\\ +  \int_{\underline \theta_S}^{\theta_S} Q_S(x)dx\right] &= \int_{\underline \theta_B}^{\overline \theta_B}\left[\int_{\underline \theta_B}^{\theta_B} Q_B(x)dx  \right]f_B(\theta_B)d\theta_B + \ldots \\
\int_{\underline \theta_B}^{\overline \theta_B}\left[\int_{\underline \theta_B}^{\theta_B} Q_B(x)dx  \right]f_B(\theta_B)d\theta_B &= \int u dv \\\
&= \int \left[\int_{\underline \theta_B}^{\theta_B} Q_B(x)dx  \right] d\left[ f_b(\theta_B)d\theta_B\right]\\
&= uv - \int vdu\\
&= \left[\int_{\underline \theta_B}^{\theta_B} Q_B(x)dx  \right] F(\theta_B)d\theta_B - \int Q_B(x)f(x)dx
\end{align}$$%%
