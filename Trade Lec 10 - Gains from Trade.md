---
aliases: 
tags: 
creation date: Monday, October 9th 2023, 1:02 pm
date updated: Monday, October 9th 2023, 2:04 pm
---
- Baseline model gives low gains, if you add reasonable elasticities <font color=#F7B801> what si baseline</font>
	- literature has yet to overturn this

Comparative Statics: the difficulty
- start with basic utility function
- from homotheticity we know there is overall price level
- that and wages gets us welfare can normalize $w_{i} = 1$, so just have $P$?
- $d \ln P_j = \sum x_{ij} (d \ln w_i + d \ln \tau_{ij})$

recall that 
$$ X_{ij} = \frac{(w_i z_{ij})^{1 - \sigma}}{\sum_k (w_k z_{kj})^{1 - \sigma}}$$

So price index:

$$\begin{align}
d \ln P_j &= \sum_i z_{ij} \frac{d \ln x_{ij} - d \ln x_{jj}}{1 - \sigma}\\
&= - \frac{d \ln x_{jj}}{1-\sigma}
\end{align}$$

So $\hat W_j = (\hat x_{jj})^{1/(1-\sigma)}$
since $\sigma > 1$, opening to trade causes domestic sales to fall, negative exponent -> welfare rises
where $\hat a= a_\text{new}/a_\text{old}$ - hat algebra

Extend to sectors. production is cobb douglas for each sector. then it's sector-by-sector Armington? 
Can add intermediate goods/inputs 

<font color=#F7B801>what does it mean 'by the gravity equation'</font>

with intermediate goods
Solve firm optimization to figure out that the price across sectors has limited interactions

Then

$$ \frac{w_j}{P_j} = \prod_s \prod_{s'} x_{jjs'}^{- \alpha_{js} \delta^s_{js'}/(\sigma_{s'} - 1)}$$
so aggregate across sectors the real wage change: increases the more that domestic production decreases
$\alpha$ is consumption share. 

The coefficient $\delta$ comes from a matrix that depicts how much sectors depend on each other for intermediate goods
$\delta$ comes from matrix $(\mathbf I - \mathbf B_j)\inv$ 
$\mathbf B_j$ has $a,b\th$ element $\gamma^a_{jb}(1 - \beta_{ja})$
$(1 - \beta)$ is the share of intermediates; $\gamma$ is cobb-douglas weight (on inputs)


<font color=#F7B801>super ambiguous on gains from trade! Not a lot happened. there is a paper on tariff wars finding minimal gains/losses</font>

No homotheticity - no price index?


Can compute changes in expenditure function with [[Micro Theory V - Welfare|CV or EV]]: 

$e_j( \mathbf p_j, U_j) - e_j( \mathbf p'_j, U_j)$ is CV 
$e_j( \mathbf p_j, U'_j) - e_j( \mathbf p'_j, U'_j)$ is EV


Envelope theorem tells you 

$$ \frac{d \ln e_j(p, U')}{d \ln p_{ij}} = x(p, e(p, U')) = \frac{p_{ij} x_{ij}}{E_j}$$
$$ e_j(p'_j, U'_j) = w'_j \bar L'_j$$
This set of ODE (for $e( \cdot, U')$) can be solved under certain circumstances


Now back to monopolistic competition with CES
Firms differ by $\bar v$ which is productivity, Pareto distributed 
so then the price index is inversely related to the weighted sum of the  

$$ P_j^{1  - \sigma} = \sum_i N_i \int_0^{\bar v_{ij}^*} \left(\underbrace{\frac{\sigma}{\sigma - 1}}_\text{constant markup} \bar v w_i \tau_{ij}\right)^{1- \sigma} g(\bar v) d \bar v$$recall - monopolistic competition means $\sigma > 1$ otherwise price goes to infinity

can differentiate to disaggregate gains from efficiency, gains from variety, extensive margin

$P_j^{1- \sigma}$ is the denominator of trade shares - to review 

a bunch of algebra gets you 

	$$ d \ln e_j = \frac{d \ln x_{jj} - d \ln N_j}{1 - \sigma - \gamma_{jj}} $$
(gains from trade here are based on homotheticity - $d \ln e_j = d \ln P_j$
As before: only domestic trade matters. Intuition: revealed preferences for goods from ROW is in the shrinking of domestic consumption share 


Under pareto can show $N_j$ does not change?
$1  - \sigma - \gamma_{jj}$ is elasticity of trade; if $\gamma$ constant /pareto
$$d \ln e_j = \frac{d \ln x_{jj}}{\varepsilon}$$


Can depart from CES but have a choke price 
still get a gravity equation (using Pareto)

we had $X_{ij} = \frac{(\tau_{ij} w_i)^{-\sigma}}{\sum_k (\tau_{kj} w_k)^{-\sigma}}$
Elasticity of trade is here
it is also in the generalized gains from trade

$$ d \ln e_j = -(1 - \eta)\frac{d \ln x_{jj}}{\theta} $$where

$$\equiv \rho \left( \frac{1 - \beta}{1 - \beta + \theta}\right)$$


Result - distortions don't necess mean welfare changes - they cancel each other out - comes from pareto (or pareto + homotheticity)

Connect to recent influential macro work: global welfare 
calculate from Armington 
$$ \sum_j X_j d\ln W_j = - \sum_j \sum_i X_{ij} d \ln \tau_{ij}$$
No production needed. 
If sales larger, then change in trade costs more impactful for welfare. 