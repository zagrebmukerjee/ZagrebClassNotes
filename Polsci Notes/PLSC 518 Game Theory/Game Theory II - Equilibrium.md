---
aliases:
creation date: Thursday, September 15th 2022, 2:58 pm
date updated: Tuesday, September 27th 2022, 2:56 pm

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