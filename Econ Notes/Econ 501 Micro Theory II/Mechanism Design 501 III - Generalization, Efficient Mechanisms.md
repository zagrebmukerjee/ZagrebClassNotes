---
aliases:
- 'Groves Mechanism'
- 'EEM'
- 'Expected Externality Mechanism'

creation date: Saturday, April 8th 2023, 11:41 am
date updated: Saturday, April 15th 2023, 11:00 am
notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#status/🚧'
---

# [[Mechanism Design 501 III - Generalization, Efficient Mechanisms]]

<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## What is Mechanism Design?

Mechanism design is also called 'reverse game theory'. At its core, that's exactly what it is. If I want to get a certain outcome from some agents, what game should I make them play such that my desired outcome is its equilibrium outcome? For instance, in the screening problem of [[Mechanism Design 501 I - Motivation, Screening Problem]], I want to discriminate between consumers based on how much they want my product. But if I offer too good a deal to the less-desirous customer, I risk making that deal attractive to the more-desirous, and thus forgoing the potential consumer surplus I could extract from them (incentive-compatibility); if I make that deal too bad, I drive them away (individual rationality). These $IC$ and $IR$ constraints will recur as characterizing the balancing act faced by many mechanism designers. 

So far we have considered various mechanisms that sellers may use to generate and maximize revenue: the screening and auction problems, which also cover scenarios of monopolist pricing, scarce good assignment etc. Now in a more general setting we can start to think about 'efficiency' of outcomes. 

### A General Representation

$I = \{ 1, \ldots, n \}$ agents. $\theta_i$ are type distributions with joint distribution $\Theta = \prod \Theta_i$. $\theta$ (the aggregate profile) is distributed according to some $M \in \Delta(\Theta)$, allowing for correlated types. 

An <font color=gree>allocation</font> $X$ is a bundle $\{(k, t_1, \ldots, t_n) \in \kappa \times \R^n\}$. Here $k$ describes the distribution of some good, generally non-monetary, such as an item being auctioned. $\kappa$ is the compact set of all nonmonetary outcomes. And $t_i$ is a monetary transfer to/from agent $i$. 

We commonly assume $\sum t_i \geq 0$ - there is no 'outside funding'. 

Let's have utility take a quasilinear form $v(k, \theta_i) - t_i$ with $v$ continuous. This is linear in the numeraire-denominated transfers $t_i$ and not necessarily linear in $k, \theta_i$. For the auctions we simply had $v(k, \theta_i) = k_i \times \theta_i$. where $k_i$ was $1$ if you get the good, $0$ otherwise. 

A <font color=gree>social choice function</font> is some $F, t$ with $F: \Theta \to \kappa$ and $t: \Theta \to \R^n$ with $\sum t > 0$. $F,t$ is <font color=gree>ex post Pareto Efficient</font> if, for ALL type profiles $\theta \in \Theta$, $\nexists k', \theta'$ such that $\forall i$ $u(k', t', \theta_i) \geq u(k, t, \theta_i)$, and for at least one $j$, $u_j(k', t', \theta_j) > u_j(k, t, \theta_j)$. That is to say, no alternative $k, t$ that makes everyone better off. 


### Efficiency Lemma

$k, t$ is Pareto efficient if and only if: 
1) $\forall \theta$ $k(\theta) \in \arg \max \sumn{i} v_i(k, \theta_i)$ (decision efficient), and 
2) $\forall \theta$, $\sumn{i} t_i(\theta_i) = 0$ (budget balance)

#### Proof:
<font color=#F7B801>by me</font>
$\implies$: Suppose k pareto efficient. Suppose for a contradiction that either ∃ k′ with better decision efficiency or that t is not budget balanced. If the former, 
$$ \sumn{i} v_i(k', \theta_i) > \sumn{i} v_i(k, \theta_i)$$ Then under $k'$ there is an aggregate lump sum of consumption utility left behind. Let $D = \sumn{i} v_i(k', \theta_i) - \sumn{i} v_i(k, \theta_i)$, so $D > 0$ Let $x = x_1, \ldots, x_n$ be the allocation of the consumption good or whatever, with $x_i$ being the value given to agent $i$ under $k$, and $x'_i$ under $k'$. Given the supposition, there are some agents with $v_i$ increasing in $x$. For all such agents, define $x''_i$ as allocating them $x_i + \epsilon/n$. Then, given that $D>0$, there is some $\epsilon$ such that this reallocation describes a Pareto improvment. 

If $t$ is not budget balanced, i.e. $\sum t_i \neq 0$, then we must have $\sum t_i > 0$, under no outside funds. But then we can simply reduce everyone's contribution by $\sum t_i/n$ and create a pareto improvement. 

$\impliedby$: Suppose the conditions hold. A Pareto improvement will increase someone's utility, and decrease no-one's: so if $k'$ is a Pareto improvement, then 
$$\sumn{i} \big( v_i(k', \theta_i) - t'_i(\theta_i)\big) > \sumn{i} \big( v_i(k, \theta_i) - t_i(\theta_i)\big)$$

So one of the following must hold: 

$$\sumn{i} v_i(k', \theta_i) > \sumn{i} v_i(k, \theta_i) \text{ or } \sumn{i}t'_i(\theta_i)  < \sumn{i}t_i(\theta_i)$$

The first is impossible, since $k \in \arg \max \sum v_i$; and the second is also impossible, since $\sumn{i} t_i(\theta_i) = 0$ and $\sumn{i} t_i$ cannot be negative (no outside funding). 



## Groves Mechanism

The Groves Mechanism is a class of mechanisms of a particular form, with desirable properties. Let $h: \Theta_{-i} \to \R$ be some arbitrary function. A Groves Mechanism has: 

$$ -t_i(\theta_i) = -h_i(\theta_{-i}) + \sum_{j \neq i} v_j(k, \theta_i, \theta_{-i}) $$
The first term is simply something that agents can't manipulate through their reports, and the second term is the externality of this agents' report on the other agents. So we are internalizing the externality by incentivizing the agent to maximize others' utiility. 

Under these circumstances, with a consumption utility maximizing $k$, the Groves mechanism has truth telling as an optimal strategy. 

### Proposition (Groves Truth-telling)

Suppose $k$ is decision-efficient, and a mechanism takes the form $(k, t_1, \ldots, t_n)$ where $t_i$ takes the Groves form above. Then a truthful report is the optimal strategy for all $\sigma_{-j}$ and is IC. 

### Proof
Suppose $\theta' \neq \theta_i$ is a better report. Then this requires: 

$$\begin{align}
v_i(k(\theta', \theta_{-i}), \theta_i) - t_i(\theta', \theta_{-i}) &> v_i(k(\theta, \theta_{-i}), \theta_i) - t_i(\theta, \theta_{-i}) \\
v_i(k(\theta', \theta_{-i}), \theta_i) -h_i(\theta_{-i}) + \sum_{j \neq i} v_j(k, \theta', \theta_{-i}) &> v_i(k(\theta, \theta_{-i}), \theta_i) -h_i(\theta_{-i}) + \sum_{j \neq i} v_j(k, \theta_i, \theta_{-i}) \\
v_i(k(\theta', \theta_{-i}), \theta_i) +\sum_{j \neq i} v_j(k', \theta', \theta_{-i}) &> v_i(k(\theta, \theta_{-i}), \theta_i)  + \sum_{j \neq i} v_j(k, \theta_i, \theta_{-i}) \\
\sumn{i} v_i(k(\theta', \theta_{-i}), \theta_i) &>  \sumn{i} v_i(k(\theta, \theta_{-i}), \theta_i)
\end{align}$$
But this contradicts the assumed decision efficiency. 


## Pivot Mechanism

The pivot mechanism is a special case of the Groves/ VCG class. In this case, you're paid based on the marginal effect of your presence. 

Define counterfactual $\kappa$ as $\arg \max_k \sum_{j \neq i} v_j (k