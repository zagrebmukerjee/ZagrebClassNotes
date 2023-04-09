---
aliases:
creation date: Saturday, April 8th 2023, 3:31 pm
date updated: Sunday, April 9th 2023, 9:25 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Mechanism Design 501 II - Framework and Revelation Principle]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## What is Mechanism Design?

Mechanism design is also called 'reverse game theory'. At its core, that's exactly what it is. If I want to get a certain outcome from some agents, what game should I make them play such that my desired outcome is its equilibrium outcome? For instance, in the screening problem of [[Mechanism Design 501 I - Motivation, Screening Problem]], I want to discriminate between consumers based on how much they want my product. But if I offer too good a deal to the less-desirous customer, I risk making that deal attractive to the more-desirous, and thus forgoing the potential consumer surplus I could extract from them (incentive-compatibility); if I make that deal too bad, I drive them away (individual rationality). These $IR$ and $IC$ constraints will recur as characterizing the balancing act faced by many mechanism designers. 

### General Formulation

$I = \{1, \ldots, n\}$ is a set of agents. Each observes $\theta_i \in \Theta_i$ privately. $\Theta \equiv \Pi \Theta_i$, the space of possible type profiles; and $\theta \in \Theta$ is one particular type profile $(\theta_1, \ldots, \theta_n)$. Profiles follow some known joint distribution $M \in \Delta \Theta$. 

$X$ is a set of allocations, where $x = (q,t)$ in the screening case, with $q \geq 0$ and $t \in \R$. Each agent has utility $u_i: \Theta_i \times X \to \R$. A social choice function $\xi: \Theta \to X$. 

Social planner has the problem that $\theta$ is not known, but it's payoff relevant, so agents might lie about it. Hence the need for a mechanism. 

A mechanism is a specification $((M_i), g)$ where $M_i$ is the set of actions available to agent $i$, with $M = \Pi M_i$, and $g: M \to X$ is the rules of the game, which maps from actions taken by each agent to allocations: the social planner observes the actions taken/messages sent by each agent, then determines the outcome. 

![[Mechanism Design 501 II - Framework 2023-04-08 14.37.53.excalidraw|200]]

The mechanism creates an incomplete information game: player $i$ has strategy $\sigma_i: \Theta_i \to M_i$, defining how she reacts to her available information, and utility $u_i(g(M), \Theta_i)$. eg. in the screening problem, we had $g$ as the price bundles, $M_i = \R$, and $g(q) = (q, p(q))$. 

Then the planner has to look at the BNE of this game, which is characterized by: 

$$ \forall i,\; \forall \theta_i \in \Theta_i\ ; \sigma_i(\theta_i) \in \arg \max_{m \in M_i} E\bigg[ u_i(g(m, \sigma_{-i}), \theta_i \bigg|\theta_i\bigg] $$
in other words, the strategies that maximize expected utility. 


## Revelation Principle

This problem is very unstructured with a huge search space. To narrow it down we can make use of the Revelation Principle. 

```ad-important
title: Definition

A <font color=gree>direct mechanism</font> is a mechanism with $M_i = \Theta_i$: one action per type. Intuitively it's a mechanism where each agent reveals a type.
```

The Revelation Principle states that: if there exists some mechanism that implements $\xi$, then there is a direct mechanism that implements $\xi$; i.e., 
$$\forall \theta_i,\theta_i', E_{\theta_{-i}}\bigg[u_i(\xi({\color{red}\theta_i}, \theta_{-i}), \theta_i \bigg| \theta_i\bigg] \geq E_{\theta_{-i}}\bigg[u_i(\xi({\color{red}\theta_i'}, \theta_{-i}), \theta_i \bigg| \theta_i\bigg] $$

