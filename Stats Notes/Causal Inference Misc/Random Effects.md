---
aliases:
creation date: Saturday, April 12th 2025, 9:44 pm
date updated: Saturday, April 12th 2025, 9:54 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Random Effects]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

From Ben Lambert's video
https://www.youtube.com/watch?v=bQampZBzU9Q
https://www.youtube.com/watch?v=EbdBHJYbOrg

Panel data techniques. 

Setup: Home prices vs Crime with time FEs

Structural equation

$$ H_{it} = \beta_0 + \beta_1 \text{Crime}_{it} + \beta_2 \text{Unemp}_{it} + \gamma_t + \alpha_i + u_{it}$$
where $\alpha_i$ and $u_{it}$ are disturbances

Problem $\alpha_i$ is related to disturbances and covariates $\text{Crime}_{it}$ so can't do pooled simple regression. $$ \cov(\alpha_i, x_{it}) \neq 0$$
One solution $\gamma_i$ fixed effects or first differences - costly (discarding one observation)

Suppose 
$$ \cov(\alpha_i, x_{it}) = 0$$then I could do pooled OLS which is unbiased and consistent (and FE, FD are as well). 

Define pooled error term $$ \eta_{it} \equiv \alpha_i + u_{it}$$
Consider two different times in same city 
$$\begin{align}
\cov(\eta_{it}, \eta_{is}) &= \cov(\alpha_i + u_{it}, \alpha_i + u_{is}) \\ 
&= \cov(\alpha_i, \alpha_i + u_{is}) + \cov(u_{it},  \alpha_i + u_{is})  \\ 
&= \cov(\alpha_i, \alpha_i) +  \cov(\alpha_i, u_{is}) + \cov(u_{it}, \alpha_i) + \cov(u_{it}, u_{is})  \\ 
&= \var( \alpha_i) +  \cov(\alpha_i, u_{is}) + \cov(u_{it}, \alpha_i) + \cov(u_{it}, u_{is})  \\ 
\end{align}$$
Even if you assume the last 3 terms are $0$, the variance of $\alpha_i$ is positive which means that there is a cluster structure (serial correlation) in the pooled OLS

Could deal with serial correlation with FGLS  by estimating serial correlations <font color=#F7B801>what is that</font>
In this paneldata case it is called random effects
it has big ol' efficiency gains