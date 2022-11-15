---
aliases:
creation date: Tuesday, November 8th 2022, 5:07 pm
date updated: Tuesday, November 15th 2022, 3:56 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Game Theory V - Signaling Games]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## Foundation

Two new concepts that we are introducing. 

#### Learning
Players using [[2002.1 Probability|Bayes' Rule]]. I have uncertainty about something eg behaviors. I want to condition and learn. 

#### Conjecture and Check
I need to conjecture a about what the players do, and then check if that makes sense strategically
- often I will find a profitable deviation.


![[Game Theory V - Signaling Games 2022-11-15 15.44.30.excalidraw]]

Basic game setup. Nature chooses state of the world. Player 2 needs to take a policy action to match state of the world but doesn't observe state. Player 1 needs to say something, having observed the state, and wants P2 to match; but player 1 pays a cost for saying state is bad


Need two strategies: 
1) Player 1 has mapping from $\{$ Good State, Bad State $\}$ to $\{$ "Good", "Bad"$\}$
2) Player 2 has from $\{$ "Good", "Bad"$\}$ to $\{$ Act, Not Act $\}$



what is rationality here? It's for player 2 to act in a way that makes sense given the 'information they have': beliefs. 
In this case, P2 has beliefs that are $P(\omega | \text{"good"})$, and $P(\omega | \text{"bad"})$ . 

Where do I get them? [[2002.1 Probability|Bayes' Rule]]
 $$ P(\omega = \text{bad}| s_1 = \text{"bad"}) = \frac{(1-\pi)P(s_1 = \text{"bad"}|\omega = \text{bad})}{(1-\pi)P(s_1 = \text{"bad"}|\omega = \text{bad}) + \pi P(s_1 = \text{"bad"}|\omega = \text{good})}$$


### Perfect Bayesian Equilibria

So equilibrium will be: 
- Strategies are sequentially rational given beliefs
- beliefs satisfy Bayes' rule. 

how to find this sort of thing: conjecture a rule for player 1, then check to see if it satisfies PBE condition

First supposition: report truthfully. 

then what is belief: 
$$P(\omega = \text{good}| s_1 = \text{"good"})  = \frac{(1-\pi)P(s_1 = \text{"good"}|\omega = \text{good})}{(1-\pi)P(s_1 = \text{"good"}|\omega = \text{good}) + \pi P(s_1 = \text{"good"}|\omega = \text{bad})} =  \frac{(1-\pi)P(s_1 = \text{"good"}|\omega = \text{good})}{(1-\pi)P(s_1 = \text{"good"}|\omega = \text{good}) + \pi P(s_1 = \text{"good"}|\omega = \text{bad})} $$