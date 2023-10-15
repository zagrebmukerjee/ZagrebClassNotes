---
aliases:
  - Roy Labor Model
  - Roy Model
creation date: 2023-10-09 16:00
date updated: 2023-10-09 16:00
notetype: Math Class Note
cssclasses:
  - math-class-note
tags:
  - "#types/classes"
  - "#status/🚧"
---

# [[Development 10-9-23]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

Deworming 
people love it. why?
- one time pill, cheap (or once a year)
- lots of kids have it
- 1.3Billion people worldwide have hookworm, roundworm <font color=#F7B801>shit</font>

Prior results show little effect - ex randomize which students in school get it
- concern about spillovers
- worms is communicable

Miguel and Kremer 2003. Randomize by group. 
3 groups , 3 periods: before;  treated/treated; control/treated; control/control

Note: takeup is like 60 percentish

Directly estimate the spillovers! look how many people from treated schools live close to you
Observation is a student in a school in a year

Infected ~ a + b1 Treated_1 + b2 Treated_2 + $\sum_\text{distance}$ gamma_dist (# of treated students)  + $\sum_\text{distance}$ gamma_dist (# of untreated students)  + school FE + error

<font color=#F7B801>Are the gamma terms the same? </font>
Under this effect, find a 25% decline in pr(infection). Bad effect from being near untreated schools: 11% per 1000 students nearby. Good effect near treated schools, 25%/1000 nearby

Can estimate: 
23 pp drop in infections
2 pp enrollment increase in nontreated
7.5 pp increase in enrollment (presented as 25% drop in absenteeism)

Treat 1 child in the school in this context = .14 boost in schooling years. 
- heavy rainfall year, big wormy time

schooling effect only there for girls?
- this is observed in every intervention
- generally girl wage flat, boy wage up - they see this in this study with same people later. 



## Gender and Human Capital 
Three stylized facts/regularities
1) Nutritiion at early ages increases schooling of girls not boys
2) level of schooling for women > that of men
3) higher estimated rate of return for women

Propose to explain this without common explanation of contraceptives. Note that this happens in places and times where contraception much less of a big deal 

class says, in bangladesh, there is big rise in enrollment that precedes micro credit. so much for that
in Bangladesh big diarrheal problem, major intervention helped fix it, at inflection point

Is there a comparative advantage women have (skills v brawn)
Policy question: what do development strategies have to do with it
3 major strats
- agricultural development
- health and nutrition
- industrialization and trade (with China)

First test of an old idea
incorporate 'brawn heterogeneity', joint effects of nutrition, schooling, activity choice
add labor market too


>[!note] Roy Labor Model
> $i$ indexes tasks.
>
>each worker - a bundle of attributes, skill and brawn $(H,B)$
>wage = $\pi(i)\nu(i)(\kappa H)^{\alpha(i)}B^{(1 - \alpha(i))}$
>where $\pi(i)$ is eqm output price, and $\alpha_i$ is increasing in $i$. More skill is bigger $i$
>task here is cobb douglas
>
>Brawn is made by $B(\gamma M) + b$ with $\gamma > 0$ and $B_M> 0$ and $B_{MM}<0$
>where $M$ is mass
>$M = M(\theta C) + m$  more calories is more mass. the $\theta$ is worms 
>$m$ is heterogenous BW endowment
>
> $H$ has no endowments. $H = H(S; \theta C)$. Mens sana in corpore sano
> $\omega(B)$ is child wage (opportunity cost of schooling)
>
workers choose jobs based on comparative advantage wrt. these attributes
Rewards to ability heterogenous by occupation
>$$\max_{C, S, i} U(\theta C, W)$$ 
>$$\text{ subject to } F + (1-S)\omega = pC + Sp$$
>where constraint is - wealth + child labor pays for food and schooling
>Returns to calories higher for men; wage goes up more, brawn up more
>
>Can find from FOC that only $H/B$ the ratio/comparative advantage is important

Then what happens here
women have more schooling from decreased $\theta$, decrease $C$, increases skill-intensity of occupations?? <font color=#F7B801>this must mean the occupations actually chosen/practiced</font>
for men increased $\theta$ may decrease schooling and skill intensity. 
When $\alpha$ rises overall, men's schooling decision responds less





note that men have a ton of brawn vs. women, and differential increasing in nutrition
no difference in 'ravens test' of cogitive ability


measurement error model and use 'GLLAM' to estimate eqn and labor market
	we find that brawn endowment in fact predicts labor market outcome for guys but not for gals