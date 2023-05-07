---
aliases:
creation date: Thursday, May 4th 2023, 6:53 pm
date updated: Friday, May 5th 2023, 10:21 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Mechanism Design 501 V - Signaling]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Setup

Problem: Worker has private type information. Chooses to send a signal or not. Prospective employer has preferences over type and offers a wage based on test outcome. Crucially the sending of the signal is easier for higher types. 

Worker payoff is $w - c(e, \theta)$ where $e$ is the signal decision. Assume $c(0, \theta) = 0$ for all $\theta$. $C_\theta, C_{\theta e} < 0$ and $C_{e} > 0$; type decreases cost and marginal cost of signal.  The worker wants to convince the firm they are the high type. In this model that's all the signal does. 

Example: Firm payoff is $\pi = -(\theta - w)^2$. Could have $\theta \in \Theta = \{ \theta_L, \theta_H\}$ and $0 < \theta_H < \theta_L$, with $Pr(\theta= \theta_H) = \lambda$ and $\lambda \in (0,1)$. So ex ante, optimal to set $w = e(\theta) = \lambda \theta_H + (1- \lambda) \theta_L$. 

Game timing: 
1) Worker observes $\theta$
2) Worker chooses signal $e$ 
3) Firm chooses $e$. 
If $\theta$ is observable then $w = \theta$, $e = 0$ for all $\theta$. It's ex post Paretian - no purely wasteful signalling is done. 


## Equilibrium 
A PBE of the imperfect information case constitutes a function $e^*: \Theta \to \R$ for the worker and $w: \R \to \R$ for the firm. For this we want beliefs over worker types, $\mu(e): \R \to [0,1]$. 

1) For all $\theta \in \Theta$ we have worker optimization: 

$$e(\theta) \in \underset{ e \geq 0}{\arg \max} w(e) - c(e, \theta)$$

2) For all $e \in \R$, 
$$w(e) = E_{\mu(e)}[\theta] = \mu(e) \theta_H + (1- \mu(e)) \theta_L$$
3) $\mu$ obeys Bayes' Rule on path: if $e = e(\theta_H) \neq e(\theta_L)$, $\mu(e) = 1$. 

### Separating Equilibrium 
It turns out that with unrestricted off path beliefs we can sustain a wide variety of equilibria. One family of those we can call 'separating equilibria', where $e^*(\theta_H) \neq e^*(\theta_L)$. So a firm precisely learns the worker type. 
- In separating PBE, the lower type sends a signal of $0$. Why bother, since a signal is costly? 
- The high type has $e_H \in [\underline e,\overline e]$. $\underline e$ is the least sign that separates the high from low type. So $c(\underline e, \theta_L) = c(\underline e, \theta_H)$. We can further conclude using the firms' perspective that this is equal to $\theta_H - \theta_L$ - the least I can pay the worker to incentivize separation. 
- At some point $\overline e$ it becomes not worthwhile to signal  for the high type. 

The firm can support any $e^*$ in $[\underline e, \overline e]$ by having an off-path belief that $e \neq e^* \implies \theta = \theta_L$. In other words, 

