---
aliases: []
creation date: Thursday, September 7th 2023, 4:07 pm
date updated: Thursday, September 14th 2023, 4:29 pm
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



---
why do this
one major application - networks want finite population analysis. 

can do a finite population central limit theorem
chen and xiao? result
- central limit theorems can be obtained like sO:
- Assume there is some $c$
$$Y_i/\pi_i \leq c \; \forall i$$
then sufficiently understand $R_i$s 
so central limit theorem can come from only the design world
also need SUTVA though. which is nontrivial! if guy 2 sees me surveying guy 1 and changes their answer...

in this case, $y_i$ being non random is in fact SUTVA

-> aside
missing data is also a causal inference problem


---
Fixed real-valued potential outcomes: 

$$y(0) = (y_1(0), \ldots, y_n(0)$$ $$ y(1) = (y_1(1), \ldots, y_n(1))$$
SUTVA: $Y_i = D_i y_i(1) + (1 - D_i)y_i(0)$
$D_i$ are not necessarily iid
We know $D$ and $Y$ but not the counterfactuals


Desideratum $\Delta$ is ATE for finite population 

$$ \Delta = \frac{1}{n} \sumn{i} \tau_i = n\inv \sumn{i} y_i(1) - y_i(0)$$
Can have $P(D_i = 1)$ the 'marginal' probability of treatment for any unit 

HT estimator is finite sample unbiased for $\Delta$ 
which is 

$$n \inv \sumn{i} \left[ \frac{Y_iD_i}{p_i}- \frac{Y_i(1-D_i)}{1 - p_i}\right]$$
In fact this is unbiased for each $Y_i$. 

-> aside
differentiate between asymptotically unbiased and unbiased asymptotically

$$\hat \theta = \begin{cases} 
\theta &\text{ with probability } n-1/n\\
\theta + N &\text{ with probability } 1/n
\end{cases}$$
so $E(\hat \theta)$ = $\theta + 1$
Always biased! 
But asymptotically unbiased


---

Example: Choose 1 of three units to treat with equal probability. 

$$ f(D) = \begin{cases}
1/3 &\text{ if } D = (1,0,0)\\
1/3 &\text{ if } D = (0,1,0)\\
1/3 &\text{ if } D = (0,0,1)\\
0 &\text{ otherwise } 
\end{cases}$$
if potential outcomes are 
$$ y(0) = (1,0,2)$$
$$y(1) = (0,0,0)$$
🚧


Note - no generally unbiased/consistent est of variance of HT estimator



