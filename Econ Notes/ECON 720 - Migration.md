---
aliases: 
creation date: Saturday, December 16th 2023, 5:41 pm
date updated: Saturday, December 16th 2023, 5:55 pm
notetype: Math Class Note
cssclasses:
  - math-class-note
tags:
  - "#types/classes"
  - "#status/🚧"
---

# [[ECON 720 - Migration]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

Want to address shortcoming of static models, which often have instant, costless mobility or perfect immobility. These models cannot address displacement, adjustment, etc (as with China shock). Incorporate dynamics into the model. 

HH decision where to supply labor - a dynamic discrete choice problem, with idiosyncratic time varying shocks. This reflects several empirical patterns - e.g the fact that gross flows are an OoM greater than net flows, and significant fraction of ppl who move willingly take a paycut. This also stops the model from being boring. 

## Model

$N$ locations, indices $i$, $n$ 

household value if located in $n$ at time $t$: 

$$ v_t^n = U(C_t^n) + \max_{\{i\}_{i=1}^N} \{ \beta E[v^i_{t+1}] - \tau^{n,i} + \nu \epsilon_t^i\}$$
subject to $U(C_t^n) = \log w_t^n$. The maximand is: what location $i$ maximizes my utility tomorrow (discounted by $\beta$), given that I pay migration costs $\tau$ based on my current location $n$, and my idiosyncratic taste shocks (an $N$-vector) $\epsilon_t^i$. 
- $\epsilon$ has Type I extreme value distribution, mean $0$. This means $$F(\epsilon) = \exp( - \exp(- \epsilon - \bar \gamma))$$
- $\nu$> 0 is dispersion of taste shocks - i.e. how much they matter. 
Employed HH supplies 1 unit of labor for the competitive wage $w_t^n$. 

Write $V_t^n$ for expected lifetime utility of worker in $n$ given uncertainty of $\epsilon$. At any point $t$ we have expected utility

$$ E[v_t^n] = E [ U(C_t^n)]  + E \bigg[ \max_{\{i\}_{i=1}^N} \{ \beta E[v^i_{t+1}] - \tau^{n,i} + \nu \epsilon_t^i\}\bigg]$$

The second term - call it $\Phi_t^i$ - is the option value of moves. Want to find it. Can use tricks and the extreme value to get 

$$\Phi_t^i = \nu \log \big[ \sumn{i} \exp (\beta V_{t+1}^i - \tau^{n,i})^{1/\nu}\big] $$
