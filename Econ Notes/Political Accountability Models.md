---
aliases:
creation date: Wednesday, February 15th 2023, 1:31 pm
date updated: Wednesday, February 15th 2023, 2:32 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Political Accountability Models]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


'There is no Republican or Democratic way of picking up the garbage" - Fiorello La Guardia
A model concept where I care about how people did in office
- thinking about re-election and a choice between candidates and challengers
- Draws on contract theory and general questions of principal-agency

Important for normative democratic theory

Differences between formal and real accountability:
- Do voters reward/sanction incumbents, and 
- Do politicians even care about that

Both formal and empirical questions


### Basic Model

Three players: voter, incumbent, challenger, are in a two-period game

Incumbent chooses effort $e_1, e_2$. Voter sees it and decides whether to re-elect, $v_1 \in \{0,1\}$. 

Politician gets rents $R$ and dislikes effort $U_J(e) = R-e$. Voter utility is $e$. 

Period 1 - incumbent chosoes $e_1$, voter decides $v_1$, new pol chooses effort

Solution concept: SPNE
Effort in period $2$ is $0$ for the subgame. So voter is prospectively indifferent between challenger and incumbent

How well can the citizen do? What's the best equilibrium? Create voting rule $\gamma: e \to [0,1]$. 

$$e_1^* \in \arg \max_{e \geq 0} R-e_1 + \delta \gamma(e) R$$
So $(e_1^*, \gamma(e_1^*), e^*_2 = 0)$ is an SPNE. What is the best $\gamma$? 
There is no loss in some $\underline e$ such that $e > \underline e \to v = 1$. 

Incumbent then can choose $\underline e$ or $0$. Anything else is strictly dominated by one of those two. Depends if $R - \underline e + \delta R > R$. So then $\underline e \leq \delta R$ so $\delta R$ is the most I can get. Effort only depends on $\delta$ and $R$ - pol has outside option of looting and leaving


Critique is that the voter needs to be indifferent between incumbent and challenger to be able to make a credible threat

### Career Concerns

Now there are types of politicians which is private information

Performance is a function of $\theta$ competence, $e$ effort and $\epsilon$ luck: 

$$ \pi_t = \theta_J + e_t + \epsilon_t$$
Competence $\sim \mathcal N(m, \sigma^2_\theta)$; no player knows $\theta_I, \theta_C$. Luck $\sim \mathcal N(0,\sigma^2)$. 
Voter utility is $\pi$, politician utility is $R - c(e)$.

Two periods, voter observes $\pi$ and chooses reelection (has observed info about pol type)
Eqm concept is Perfect Bayesian Equilibrium. Voter has to try and use $\pi_1$ to learn about $\theta_I$. Bayes time: 
$$ P(\theta_C = \theta_1|\pi_1 = p) = \frac{P(\pi = p | \theta_C = \theta_1)P(\theta_C = \theta_1)}{P(\pi_1 = p)} $$
So now there is an equilibrium $\underline \pi$ that emerges from the Bayes' rule: and an equilibrium is $e^*, \underline \pi$ such that 
- $e_1^* \in \arg \max_{e \geq 0} R P(\pi_1 > \underline \pi | e = e_1^*) - c(e_1^*)$
- $\pi_1 > \underline \pi$ iff incumbent has higher ability than random challenger (ie above-mean type).


To solve can have some nice priar $e_1^a$ with posterior then distributed $\theta_I|(\pi_1, e_1 = e_1^a) \sim N(\bar m, \sigma^2_\theta (1-\lambda))$
with 

$$ \bar m = \frac{\sigma^2_\theta}{\sigma^2_\theta + \sigma^2_\epsilon}(\pi_1 - e_1^a) + \frac{\sigma^2_e}{\sigma^2_\theta + \sigma^2_\epsilon}m$$
with $\lambda = \frac{\sigma^2_\theta}{\sigma^2_\theta + \sigma^2_\epsilon}$

Now we are not indifferent - vote if $\bar m > m$, and so $\pi_1 \geq m + e_1^a$ which is $\underline \pi$. Election becomes 'selection' mechanism on competence of candidate. 

Incumbent puts in effort to maximize $R P(\pi_1 \geq \underline \pi | e_1) - c(e_1)$. Can expand condition $P(\theta_I + \epsilon_1 \geq \underline \pi - e_1|e_1)$, recalling I don't know my type. Two indep normals: $\theta_I + \epsilon_1 \sim N(m, \sigma^2_\theta + \sigma^2_\epsilon)$. SO I have something to maximize for poltiician 

maximize for the politician 
voter is not fooled - $e_1^a = e_1^*$. 
get FOC and solve to get:
$$ \frac{R}{\sigma^2_\theta + \sigma^2_\epsilon} \Phi(0) = c'(e_1^*)$$


### Model by Besley

Policy choice is $L$ or $R$. Types are good and bad. Good type wants what you want, bad type wants the opposite of what you want
There is some underlying state of the world: is it better to do $R$ or $L$. Politician knows state of the world better than voter (ie has special knowledge)


I wake up in the morning and see politician has chosen $R$: I observe outcomes; if I get bad outcomes from $R$, did he choose $R$ because he is bad guy or because I was unlucky?


### Pandering Models

Voter selection creates negative incentives for politicians??

Two period game with $\delta$. Voter, incumbent, challenger. Office holder decides $x_t \in \{0,1\}$ each term. Then voter decides to reelect. 

Unknown state $\omega_t \in \{0,1\}$ iid; prior probability $Pr(\omega_t = 0) = \pi > 1/2$. 
Politicians get signal 
HQ politicians learn perfectly state of world
LQ politician learns state with noise (still better than citizens) 

Voters' priors for incumbent $P(\tau_I = h) = \kappa$, challenger $\gamma$


Voter wants a match - utility $1$. Politician wants the right policy! same utility as citizens. How nice. But only gets payoff if getting reelected. 


Period 2 choice. Everyone wants to follow their signal, no conflict of interest. Payoff for electing challenger vs incumbent 