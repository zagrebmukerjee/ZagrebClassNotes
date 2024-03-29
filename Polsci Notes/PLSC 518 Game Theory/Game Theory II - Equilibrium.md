---
aliases:
- 'public good'
creation date: Thursday, September 15th 2022, 2:58 pm
date updated: Tuesday, October 18th 2022, 3:55 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#topics/methods/formal' 
- '#status/🚧'
---

# [[Game Theory II - Equilibrium]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[PLSC 518 Game Theory Index]]

## Nash Equilibrium

A Nash Equilibrium is a particular kind of solution concept for a game. Intuitively it represents a situation where nobody can benefit from changing their strategy while others keep doing the same thing. 

$s^* = (s_1^*, s_2^*, \ldots)$ is a Pure Strategy Nash Equilbrlim if $\forall$ players $i$, $\not \exists s_i'$: $u_i(s_i', s^*_{-i}) > u_i(s_i^*, s_{-i}^*)$. 

NOTE the strict inequality. can have indifference

Corollary: A Nash equilibrium necessitates no player is playing a strictly dominated strategy. 

The classic example is prisoner's dilemma:

|         | Confess | Silent  |
| ------- | ------- | ------- |
| Confess | -4, -4  | -2, -10 |
| Silent  | -10, -2 | -3, -3  | 

NE is that both players confess. Both silent is not NE; either player is better off confessing. 

There can be more than 1 NE
|      | Left | Right |
| ---- | ---- | ---- |
| Up   | 2, 2 | 0,0  |
| Down | 0,0  | 1,1  |
Here both up, left and down, right are NE. 

## Mixed Strategy Equilibrium

Consider this game:

|      | odd  | even   |
| ---- | ---- | ------ |
| odd  | 1,0  | 0,1    |
| even | -c,1 | 1-c, 0 | 

No pure strategy equilibrium exists. 

One of Nash's major contributions was to point out that players aren't restricted to pure strategies; they can instead construct a randomization rule. 

Does such a randomization rule exist? 

For that to be true, we need an indifference condition. I need everyone else's randomization strategy to satisfy a condition that would make me indifferent between options. 

#status/section/🚧 

<font color=#F7B801>elimination of dominated options also</font>


## Public Goods Problem

### Problem Formulation

Canonical problem in political science. Someone being murdered outside your apartment building. Some cost $c$ to calling the police. If anyone calls the police there is a collective benefit - everyone gets $1$. The good is nonexcludable. 

$n$ players decide to call or not call. Payoff is $1-c$ if you make call. $1$ if someone else does. $0$ otherwise.
- If $c < 1$ then there is an NE when any one person is calling - so $n$ of them. 
- But what about coordination? 
	- What's the internal story - how does everyone else know that the caller is calling
	- How do you decide who is calling - which of the $n$ are we playing. 

Game theory lingo: These equilibria are very <font color=gree>asymmetric</font>. There's nothing in the model that tells you why some particular person is calling. Why did you pick this one?

But none of the <font color=gree>symmetric</font> profiles are NE for $n>1$ (ie. nobody calls or everyone calls). 

### Mixing

So if I want a symmetric equilibrium, I am SOL? Let's look at symmetric mixed strategies. 

Suppose a player chooses some $\sigma_i$. I require that all $\sigma_i = \sigma$ for symmetry. I require that each player be indifferent between calling and not based on others' $\sigma$. 

For some $i$, I have $E(u_i|s_i = \text{call}) = 1-c$. I have $E(u_i|s_i = \text{no call}) = 1-(1 - \sigma)^n$. So I need $1 - (1- \sigma)^{n-1} = 1-c$; and so $\sigma = 1 - c^{1/(n-1)}$. 

Don't need to solve it to say that some $\sigma$ exists (given $0 < c < 1$) 0 can establish that $\sigma = 0$ has RHS $0$, and $\sigma = 1$ has RHS $1$. So I can say something exists by the intermediate value theorem. This is a sort of comparative static - I'm interested in how the result varies with $c$ and $n$, or I am interested in making inference about $c$ and $n$ having made observations of $\sigma$ 

Note! Equilibrium condition is $1-c = (1- (1-\sigma)^{n-1})$. LHS is probability of public good being provided. It stays constant in $n$ - by this condition. So public good provision is the same in kansas and NYC. I can make this claim without solving for $\sigma$. 

### Complexity

In the last problem we said it takes any $1$ person to call to obtain the good. now we say that we need $k$ people to make the call (where $k < n$). There are still PSNE - $k$ players call - but they are still asymmetric. This time though, there is a symmetric NE: nobody calls. 


```ad-example
title: Two Candidate Effort Contest

```

#### Setup

Two candidates can exert positive effort. The effort costs $\beta_1, \beta_2$ for each candidate, where $0 < \beta_1 < \beta_2$. The candidate who exerts more effort wins a utility of $1$. Pay your effort regardless.  

What are the equilibria?

#### Argument
1) Most I will spend is $s_i$ such that $1 = \beta_i s_i$. Call it $\bar s_i = 1/\beta_i$. So support of a distribution over candidate $i$'s strategy is at most $[0, 1/\beta_i]$. 
2) Since $\beta_2 > \beta_1$, $1/\beta_1 > 1/\beta_2$. So $s_1 > 1/\beta_2$ wins with certainty. But for all $s_1 > 1/\beta_2$ there is some $1/\beta_2 < s_1' < s_1$ that is better. So $s_1 \notin (1/\beta_2, \infty]$. 
3) If $s_1 = 1/\beta_2$, and $s_2 = 1/\beta_2$ with positive probability (NOT positive density) then there is a positive deviation for player 1 - so $P(s_2 = 1/\beta_2) = 0$. 

Now can we write indifference conditions?

$$\begin{align}
EU_2(s_2) &= EU_2(s_2') \text{ for } s_2, s_2' \in [0, 1/\beta+2]\\
&= - \beta_2 s_2 + P(s_1 < s_2) = - \beta_2 s_2' + P(s_1 < s_2')\\
\beta_2(s_2' - s_2) &= F_1(s_2) - F_1(s_2') \text{ so the CDF has linear form }\\
f_1(s) &= \beta_2\\
EU_1(s_1) &= EU_1(s_1') \\
\beta_1(s_1' - s_1) &= F_2(s_1') - F_2(s_1)\\
\end{align}$$
but now we have a problem - the integral of my candidate density, $f_2(s) = \beta_1$, is only $1 - \beta_1/\beta_2 < 1$. Where is the rest of the dang probability? We know that it's not $1/\beta_2$. 
Suppose I've shown there's no gaps, and no random points in the interior of the interval with positive probability. Then I get $P(s_2 = 0) = 1 - \beta_1/\beta_2$. 
So can I say that? 
With any single point having positive probability for player 2, player 1 can play a little bit higher, so we'd need a hole around that single point in $F_1$. but then the point doesn't make sense for player 1.  


$EU_1(0) = \frac{1}{2}(1 - \beta_1/\beta_2)$; $EU_1(s) = P(s_2 = 0) + \beta_1 s - \beta_1 s = 1 - \beta_1/\beta_2$. So this is somewhat of a problem. I need to then have a tiebreaker rule that says, if both players play 0, 1 has to win the tie. But this tie has zero probability . 

 





## Nash Existence Theorem

### Setup

Suppose $N$ finite, and $S_i$ finite for each $i \in N$. 

A mixed strategy for $i \in N$ is a lottery over $S_i$. Suppose $S_i = (s_1, s_2, \ldots s_K)$. Then $\sum^K \sigma_k$ is $1$. This constraint looks like some sort of $n$-dimensional equivalents of the tetrahedron $z = 1 - x - y$. Call this a simplex: then we can say $\sigma_i$, some mixed strategy, is a vector that lies on the $d-1$ dimensional simplex $\Delta(S_i)$. 

Write $\sigma^* = (\sigma_1^*, \sigma^*_2, \ldots)$. Then I need $\sigma_i^* \in b(\sigma^*_{-1})$: my strategy has to be a best-response to everyone else's mixed strategy 

Define $b(\sigma) = [b_1(\sigma_{-1}), \ldots, b_N(\sigma_{-N})]$. This is the best response for each player conditional on others playing $\sigma$ (some vector). Then $\sigma^*$ is an MSNE if $\sigma^* \in b(\sigma^*)$. This is a <font color=gree>fixed point</font> (a point that some function maps to itself)

Simplex is closed, bounded, convex. 

Key question. Is $b_i(\sigma_{-i})$ a function? We have frequently had best-response correspondences. 


### Kakutani's Fixed Point Theorem
- if $A$ is compact, convex nonempty set (for our purposes, compact being closed and bounded on RN by heine-borel thm)
- and $C$ is an [[Micro Theory IIIb - Hemicontinuity|upper hemicontinuous]] convex valued correspondence
- then $C: A \to A$ has a fixed point. 


In our case, $A$ is the set of simplexes $\Delta S_i$ and so on - the sets of possible randomization strategies. $A$ is nonempty, compact, convex. 

Convex-valued function makes sense. If I am indifferent between mixed strategies $\sigma$ and $\sigma'$ I should be indifferent between any linear combination of the two. And if $\sigma \in b(\cdot)$ and $\sigma' \sim \sigma$, $\sigma' \in b(\cdot)$. 



### Berge/Maximum Theorem

![[Micro Theory III - Demand, Duality and Decomposition#Maximum Theorem]]



### Proof (sketch) of Nash Existence Theorem

Nash result: $\Gamma = <N, S, U>$, with $N$ and $S$ finite. Then mixed strategy NE exist. 

what might be useful: $N$ finite, $S \in \R^N$ convex and compact, $u$ continuous and [[Micro Theory IIIa - Concave, Convex, Quasi|strictly quasiconcave]] (to get existence of unique best-responses)

Then $b_i(s_{-i})$ is continuous and single valued. Then I can just use a regular ol fixed point theorem. 
