---
date updated: 2021-12-27 13:06

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes/stats/causalinf'
---

# [[Basic Causal Model]]
Part of [[@Stats Index]]

Drawing on [[Angrist and Imbens 1995 Identification and Estimation of Local Average Treatment Effects]]



### Causal model:
$Y_0$ and $Y_1$ are outcomes if untreated/treated. $D$ is indicator for treatment. We observe $D$ and $Y = Y_D = D\cdot Y_1 + (1-D)\cdot Y_0$; that is to say, for each observation we see $Y_1$ if treated and $Y_0$ if not. 

We are interested in effect of treatment. Obstructed by the  the _fundamental problem of causal inference_: can never observe $Y_1-Y_0$ for the same observations, i.e. the counterfactual.

Proxy counterfactual with other observations - compute average treatment effects. 

One variable of interest: 
$$\alpha_0 = E[Y_1-Y_0]$$
Average treatment effect for the whole population. 

Can we measure this from a sample with the sample's ATE? Not necessarily:

$$E[Y_1|D=1] - E[Y_0|D = 0]$$

Doesn't become $E[Y_1-Y_0]$ unless treatment is independent of other covariates. (e.g. people can self-select into experimental medication). So $Y_1$ and $D$ are not independent.

Also can be interested in ATT: average treatment effect on the treated. Which is $E[Y_1 - Y_0|D=1]$. What effect did the medicine have on those who took it? Also hard to observe without counterfactual. 
