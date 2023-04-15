---
aliases:
creation date: 2023-04-15 16:00
date updated: 2023-04-15 16:00

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
The feasible allocations can be described as $X = \{q, t\}$ where $q = Pr($trade$)$ and $t$ is the price paid, with $\sum t_i \geq 0$ (no outside funding). The buyer utility is $\theta_b - t_b$, and the seller utility is $t_s - \theta_s$. $\theta_i$ has distribution function $F_i$ with support $[\underline \theta_i, \overline \theta_i]$, with $\Theta = \Theta_b \times \Theta_s$. 

A direct mechanism is a pair of functions, $q: \Theta \to [0,1]$ and $t:\Theta \to \R^2$. $q$ is decision efficient if $q = 1$ when $\theta_b >\theta_s$ and $0$ otherwise. Budget balance in this case just means $t_b = -t_s$: no frictions. As shown in [[Mechanism Design 501 III - Generalization, Efficient Mechanisms]], these two conditions are equivalent to ex-post Pareto efficiency. 

Define $\overline q(\theta_i) = E[q(\theta_i, \theta_{-i}|\theta_i]$
