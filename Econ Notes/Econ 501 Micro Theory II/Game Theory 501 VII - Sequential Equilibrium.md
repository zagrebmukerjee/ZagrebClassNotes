---
aliases:
creation date: Thursday, March 2nd 2023, 1:35 pm
date updated: Thursday, March 2nd 2023, 2:06 pm

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


Suppose that $\mu_3(x) =1$; then Player $3$ will play $L_3$ at $x$ or $x'$. So Player $1$ will prefer to play $L_1$; Player $2$ playes $R_2$; we're all set with sequential rationality. The above then is a PBE: I don't need to check Bayes' Rule because everything is off the path except $L1$. 


But $R_2$ dominates $L_2$ conditional on reaching this subgame. So it doesn't seem very reasonable for Player $3$ to hold this belief (on which the whole equilibrium hinges). This is a subgame imperfection that PBE doesn't pick up (we could say that the stated intention to play $s_2 = R_2, s_3 = L3$ is not credible). 

This example serves to demonstrate that PBE and SPNE may be overlapping categories, but neither contains the other. 


### Signaling What You Don't Know

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


## Sequential Equilibrium

```ad-warning
title:
Warning: despite years of efforts by pointy-headed theory nerds, this concept is not extensible to infinite extensive forms. 
```


We might be able to salvage PBE: we could add 'don't signal what you don't know', and also subgame perfection or something. At this point, though, why not ditch this frankenconcept and come up with a new one? 

This new concept is called 'sequential rationality' and addresses the problems with PBE by tackling the issue of off-path beliefs by mixing a little bit over everything; but then uses a clever limiting trick to avoid suggesting that players e.g. play strictly dominated strategies with positive probability. 



$\sigma, \mu$ constitutes a <font color=gree>consistent assessment</font> if there exist sequences of strategies/beliefs $\sigma_n, \mu_n$ such that 
1) $\sigma_n$ implies $\mu_n$ by Bayes' Rule; 
2) $\sigma_n \to \sigma$; and 
3) $\mu_n \to \mu$. 
A sequential equilibrium occurs when $\sigma, \mu$ are best responses, but also that $\sigma_n$ and $\mu_n$ exist. We do not require that $\sigma_n$ and $\mu_n$ be sequentially rational. The trick is using the sequence $\sigma_n$ to put a bit of positive probability on every strategy, and then have that go away as needed. 


### Solve t