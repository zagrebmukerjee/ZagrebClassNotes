---
aliases:
creation date: Thursday, March 2nd 2023, 1:35 pm
date updated: Thursday, March 2nd 2023, 1:56 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Game Theory 501 VII - Sequential Equilibrium]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

Some problems arise with [[🚧Game Theory 501 VI - Imperfect Information#Perfect Bayesian Equilibrium|Perfect Bayesian Equilibrium]] (ie. sequential rationality and Bayes' Rule). These problems motivate the development of a new solution concept, 'Sequential Equilibrium'. 


## Imperfections of Perfect Bayes


### Subgame Misbehavior

![[Game Theory 501 VII - Sequential Equilibrium 2023-03-02 13.58.13.excalidraw]]


### Signaling what you don't know

Consider the following game:

![[Game Theory 501 VII - Sequential Equilibrium 2023-03-02 13.38.13.excalidraw]]

Recall that a PBE constitutes an <font color=gree>assessment</font>: a combination of $\sigma$, a strategy profile, and $\mu$, probability distributions over nodes in information sets representing the beliefs of players. These must mutually satisfy sequential rationality and Bayes' Rule.

But we get into trouble when off-path; you can't condition on probability-zero events. 

In the above game, Nature moves $L$ or $R$. Player $1$ has no information about what nature has done. Both Player $1$ and Player $2$ must have some $\mu$. In particular, suppose $\mu(x) = 1/4$ and $\mu(x') = 3/4$; Player $2$ believes that we're on the left of the graph with only $1/4$ probability. Is this compatible with Bayes' Rule? Yes: the Bayes' Rule restriction is that 

$$\begin{align}
\mu(x) &= \frac{P(s_N = L \cap s_1 = R_1)}{P(s_N = L \cap s_1 = R_1) + P(s_N = R \cap s_1 = R_1)}\\
&= \frac{(1/3)0}{(1/3)0 + (2/3)0}\\
&= ???
\end{align}$$

We can't use Bayes' Rule here because we are off the path. But intuitively this makes no sense. By conditioning on $s_1 = R_1$, I am somehow changing my prior on whether $s_N = L$ or $R$. How can Player $1$'s behavior signal information about something which she herself doesn't know? In fact, it's quite possible to create payoffs in the above graph such that Player 2's belief incentivizes Player $1$ to choose $L_1$. (eg. $R_1 L_2 \succ_2 R_1 R_2$ if $s_N = L$, so $s_2 = s_2$;  but $R_1 L_2 \prec_1 L_1 \prec  R_1 R_2$, so $s_1 = L_1$.)


So this motivates another solution concept desideratum: Nobody should be able to signal something they don't know. 

