---
aliases: 
creation date: 2023-11-15 16:04
date updated: 2023-11-15 16:04
notetype: Math Class Note
cssclasses:
  - math-class-note
tags:
  - "#types/classes"
---

# [[Development 11-15]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

Paper. Just looking at the model, really get into it
notation is a big part of the cost

three components, building from the bottom


when you write a model. look at other models but build your own. when people (esp PhD students) take one off the shelf, it inevitably feels forced
Two cultural traits ${a,b}$
Equally sized populations of adult males, females.
2 period lifespan - regular, parent
1 family -> 1 boy 1 girl child. so demographics stationary


Kid is born as cultural naif/blank state
if parents are homogamous - same group - parents choose effort to socialize the kid first. Vertical socialization. 
They'll solve that, then solve the marriage market 

>write a nice model and then go to the data. that's not what we do! This isn't physics. 

child inherits trait with probability that's increasing in effort $\tau^a$ or $\tau^b$. If not, is still naif -> gets $i$ with probability $q^i$, pop share of $i$. 
Cost $H(\tau^i)$ increasig and convex, $H(0) = 0$. Effort choice. 

So parents do a backward induction type: depending on what happens. <font color=#F7B801>immediate conclusion is that minorities try super hard to socialize their child. But then what are the dynamics</font>

Let $V^{ij}$ be parent of type $i$ utility from chil of type $j$, so $i \neq j \implies $V^{ii}> V^{ij}$

Then utility maximand is straightforward: 
$$[\tau^i  + (1 - \tau^i) q^i] V^{ii} + (1 - \tau^i)(1 - q^i)V^{ij}$$
So indirect function then is $W^{ii}(q)$ which is EU for type $i$ in homogamous marriage. 
EU for parent in heterogamous - no agreement, so 
$$W^{ij}(q) = q^iV^{ii} + (1-q^i)V^{ij}$$
in eqm, $\tau>0$ and so $W^{ii}(q) > W^{ij}(q)$. can see this differentiating $W^{ii}$. 
So all agents want to match in restricted pool. only date coethnics. 
cost of entry is increasing + convex in probability $\alpha^i$, $C(\alpha^i)$. effort in eqm is decreasing as $q^i$ increases - not necess to be homogenous.  
or match in common pool
The stochasticity lets u get rid of individual heterogeneity

Cost - your optimal partner in pool will be almost certainly less nice than outside the pool
<font color=#F7B801>is there an externality? strategic decision</font>
$A^i$ and $A^j$ are probs that individuals are matched in restricted pools

So prob of homogamous marriage for someone in common pool: 

$$\Pi = \frac{(1 - A^i)q^i}{(1 - A^i)q^i + (1 - A^j)q^j}$$
so prob of homogamous marriage is 
$$ \alpha^i + (1 - \alpha_i)\Pi$$
argument from symmetry shows NE $\alpha^i = A_i$, $\alpha^j = A^j$ 

then choose $\alpha^i$ based on backwards induction on child decision

then solve out for eqm $\alpha, q$, and $\pi^i$, prob that someone in $i$ world will have homogam 

### Dynamics
now we have $q^i_t$. Probability that father trait $i$ -> kid with type $i$ is $P_{ii}\pi^i (q^i)[\tau] + (1 - \pi^j(q^i))q^i$