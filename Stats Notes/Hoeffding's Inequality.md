---
aliases: 
tags: 
creation date: Monday, May 23rd 2022, 7:33 pm
date updated: Monday, May 23rd 2022, 7:40 pm
---

---
aliases:
creation date: 2022-05-23 19:34
date updated: 2022-05-23 19:34

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Hoeffding's Inequality]]

## Statement

Let $X_1, \ldots, X_n$ be independent RVs with bounds, $a_i \leq X_i \leq b_i$ 

Let $S = \sum_i X_i$, then $E[S] = \sum_i E[X_i]$ by linearity. Then

$$P(|S - E(S)|>t) < 2\exp \left[ -\frac{2t^2}{\sum_i (b_i - a_i)^2} \right]$$
NOTE: $X$ do not need to be identically distributed

## Proof
<font color=#F7B801>left as exercise</font>


## Example 
Suppose $100$ independent $X_i$ with mean $.5$ have support $[0,1]$, and $S$ is their mean. Then we can bound the probability that $ S < .75$:

$$P(|S - E(S)|>t) < \exp \left[ -\frac{2t^2}{\sum_i (b_i - a_i)^2} \right]$$
$$ P(|S - E(S)|>.25) < 2\exp \left[ -\frac{1/8}{100} \right] = $$
