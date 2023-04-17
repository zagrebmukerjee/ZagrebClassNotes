---
aliases:
creation date: Monday, April 17th 2023, 5:02 pm
date updated: Monday, April 17th 2023, 5:11 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#types/classes/stats'
- '#status/🚧'
---

# [[Econometrics 551 VII - Instrumental Variables]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## Motivation

Instrumental variables are a very popular way to deal with endogeneity. Consider a common problem - that of omitted ability bias in determining the effect of schooling on wages. 

$$ Y = \ln w $$
$$ w = p_H \exp[\beta_1 S] \exp[\gamma A] \exp u $$
$$ Y = \ln p_H + \beta_1 S + \gamma A + u$$

Here $w$ is income, $p_H$ is price of human capital, $S$ is schooling, $A$ is ability, and $E[Su] = E[Au] = 0$. 

```ad-note
title: Aside

"Economists doing semi-structural work will reverse engineer a model to correspond (in linearity) to the regression they're going to run." - Ed Vytlacil
```

I can write this also as $Y_i = \beta_0 + \beta_1 S_i + e_i$ where $e = (u - Eu) + \gamma(A - EA)$ - note I've separated $u$ and $\gamma A$ into average parts that will be in $\beta_0$ and individual variation which will be in my error term. But I have a problem: 

$$\begin{align}
E[eS] &= E[((u - Eu) + \gamma(A - EA))S] \\
&= E[Su] - E[S]E[u] + \gamma E[SA] - \gamma E[A]E[S] \\
\end{align}$$
