---
aliases:
- 'public good'
creation date: Thursday, September 15th 2022, 2:58 pm
date updated: Tuesday, September 27th 2022, 3:38 pm

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

## Public Goods Problem

Canonical problem in political science. Someone being murdered outside your apartment building. Some cost $c$ to calling the police. If anyone calls the police there is a collective benefit - everyone gets $1$. The good is nonexcludable. 

$n$ players decide to call or not call. Payoff is $1-c$ if you make call. $1$ if someone else does. $0$ otherwise.
- If $c < 1$ then there is an NE when any one person is calling - so $n$ of them. 
- But what about coordination? 
	- What's the internal story - how does everyone else know that the caller is calling
	- How do you decide who is calling - which of the $n$ are we playing. 

Game theory lingo: These equilibria are very <font color=gree>asymmetric</font>. There's nothing in the model that tells you why some particular person is calling. Why did you pick this one?

But none of the <font color=gree>symmetric</font> profiles are NE for $n>1$ (ie. nobody calls or everyone calls). 

So if I want a symmetric equilibrium, I am SOL? Let's look at symmetric mixed strategies. 

Suppose a player chooses some $\sigma_i$. I require that all $\sigma_i = \sigma$ for symmetry.  I require that each player be indifferent between calling and not based on others' $\sigma$. 

For some $i$, I have $E(u_i|s_i = \text{call}) = 1-c$. I have $E(u_i|s_i = \text{no call}) = (1 - \sigma)^n$. So I need $(1- \sigma)^n = 1-c$; and so $\sigma = (1-c)^{n




## Nash Theorem
