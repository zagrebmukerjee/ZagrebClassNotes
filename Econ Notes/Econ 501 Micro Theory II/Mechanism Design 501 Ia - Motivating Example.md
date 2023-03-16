---
aliases:
creation date: 2023-03-16 14:11
date updated: 2023-03-16 14:11

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Mechanism Design 501 Ia - Motivating Example]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

From [[Fudenberg and Tirole 1991 Game Theory|Fudenberg and Tirole 1991]].

Suppose a monopolist faces one consumer, and has to decide what to produce (at cost $c$) and charge. The consumer's utility takes the form $\theta V(q) - T$ where $V'>0$, $V''<0$, $T$ is a transfer to the seller, and $\theta$ is some constant. Then the monopolist faces a simple problem. Charge $T = \theta V(q)$. The profit maximization is $\theta V(q) - cq$; so $\theta V'(q) = c$ gives profit maximizing $q$. 

But suppose that information is imperfect so that the consumer is type $\overline \theta$  with probability $\bar p$ and $\underline \theta$ with probability $\underline p$. with $\overline \theta > \underline \theta$. The monopolist then has to produce a price schedule detailing bundles $\overline q, \overline T$ and $\underline q, \underline T$  for the consumer to choose between. 

The goal of the monopolist is to maximize expected profit, which is $\bar p (\overline T - c \overline q) + \underline p (\underline T - c\underline q)$. 

This takes the form of a constrained optimization, with four constraints. The first two are that both types of consumers should want to make a posit
