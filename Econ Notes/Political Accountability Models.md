---
aliases:
creation date: 2023-02-15 13:32
date updated: 2023-02-15 13:32

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

Incumbent then can choose $\underline e$ or $0$. Anything else is strictly dominated by one of those two. Depends if $R - \bar e + \delta\gamma(\underline e)R > R$. 


