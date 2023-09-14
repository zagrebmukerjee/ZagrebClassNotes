---
aliases: []
creation date: Thursday, September 7th 2023, 4:07 pm
date updated: Sunday, September 10th 2023, 1:51 pm
notetype: Math Class Note
cssclasses:
  - math-class-note
tags:
  - "#types/classes"
  - "#status/🚧"
---
# [[508 1 - Sampling Theory]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

instead of estimating $\tau_i$ estimate 

$$\frac{ E[p_i(1-p_i) \tau_i]}{E[p_i(1-p_i)]} =\frac{E[V(D_i|X_i) \tau_i}{E[V(D_i|X_i)]}$$
variance weighted - which handles lack of positivity?



## Sampling Theory (Neyman 1934)

### HT Estimator

'Design Based Inference' -> units and their response schedule are fixed. no 'superpopulation', no spillovers
A random sampling design
Want to understand distr of some $y$ in population
Write $y = y_1, \ldots, y_N$ as this fixed vector of $y$; $R = R_1, \ldots, R_N$ where $R_i \in \{ 0,1\}$ is whether $i$ gets sampled. These are random, NOT iid. 

Can observe $R$ and $yR$. 

So we only learn $y_i$ if $R_i = 1$. 
$yR$s are not independent necessarily, tho if $R_i \indep R_j$ then we do have that. (b/c $y$s are just numbers)

Clustering, dependence etc comes from assignment

There is a real number $\mu = \sumn{i} \frac{1}{N} y_i$ which we want
There is some joint distributions of the $R_i$s. We can look at the marginals, $\pi_i Pr(R_i = 1)$ or $E[R_i]$; assume $>0$ for all $i$. 


$$ \hat \mu_{1, HT} = E\left[ \sumn{i} \frac{1}{\pi_{1i}}R_i Y_{1i}\right] = \sumn{i} \frac{1}{\pi_{1i}} E[R_i] Y_i = \sumn{i} \frac{1}{\pi_{1i}} \pi_{1i} Y_i = \sumn{i}  Y_i$$
shd be able to find out that you can get an unbiased estimator of treatment effect with $n=1$

Variance of HT is computable with $\pi_i$ and also $\pi_{ij}$ 


What about our nice properties like asymptotics and such, in this 'finite population' world
- we have two kinds of consistency. Finite-population consistent/Fisher consistent means: if I sample everyone I will get exactly the right answer
- Also design consistency. if the population grows large, and the sample grows in some specified way, then this converges in probability to truth


But HT sucks! Not location invariant. Very high estimate. 

### Hajek Estimator

Pronounce Hayek

$$ \hat \mu_{Haj} = \frac{\sumn{i} y_i R_i/\pi_i}{\sumn{i} R_i/\pi_i}$$ Top is 'design consistent' for $\mu$, bottom is design consistent for $1$. So this converges in probability (by CMT) to $\mu$. 


## Neyman Causal Inference (1923)


Fixed population; randomly assign treatment. A good setup for the 'real world' experimental case. 
Can also conceptualize this as three treatment arms - treatment, control, unsampled...


--- 

iid assumption codifies the idea that the sample is representative of some population. want to generalize to units like that. 



IV

many instruments: complier the same 
then I can evaluate the instruments with agreement


or if you have multiple outcomes. I know sometimes the answer is zero. if I get nonzero. 
