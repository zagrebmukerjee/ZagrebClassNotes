---
aliases:
creation date: Saturday, April 8th 2023, 11:41 am
date updated: Friday, April 14th 2023, 10:26 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#status/🚧'
---

# [[Mechanism Design 501 III - Generalization and Efficiency]]

<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## What is Mechanism Design?

Mechanism design is also called 'reverse game theory'. At its core, that's exactly what it is. If I want to get a certain outcome from some agents, what game should I make them play such that my desired outcome is its equilibrium outcome? For instance, in the screening problem of [[Mechanism Design 501 I - Motivation, Screening Problem]], I want to discriminate between consumers based on how much they want my product. But if I offer too good a deal to the less-desirous customer, I risk making that deal attractive to the more-desirous, and thus forgoing the potential consumer surplus I could extract from them (incentive-compatibility); if I make that deal too bad, I drive them away (individual rationality). These $IC$ and $IR$ constraints will recur as characterizing the balancing act faced by many mechanism designers. 

So far we have considered various mechanisms that sellers may use to generate and maximize revenue: the screening and auction problems, which also cover scenarios of monopolist pricing, scarce good assignment etc. Now in a more general setting we can start to think about 'efficiency' of outcomes. 

### A General Representation

$I = \{ 1, \ldots, n \}$ agents. $\theta_i$ are type distributions with joint distribution $\Theta = \prod \Theta_i$. $\theta$ (the aggregate profile) is distributed according to some $M \in \Delta(\Theta)$, allowing for correlated types. 

An <font color=gree>allocation</font> $X$ is a bundle $\{(k, t_1, \ldots, t_n) \in \kappa \times \R^n\}$.  Here $k$ describes the distribution of some good, generally non-monetary, such as an item being auctioned. $\kappa$ is the compact set of all nonmonetary outcomes. And $t_i$ is a monetary transfer to/from agent $i$. 

We commonly assume $\sum t_i \geq 0$ - there is no 'outside funding'. 

Let's have utility take a quasilinear form $v(k, \theta_i) - t_i$. This is linear in the numeraire-denominated transfers $t_i$ and not necessarily linear in $k, \theta_i$. For the auctions we simply had $v(k, \theta_i) = k_i \times \theta_i$. where $