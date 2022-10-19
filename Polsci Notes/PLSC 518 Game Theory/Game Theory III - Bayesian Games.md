---
aliases:
creation date: Tuesday, October 4th 2022, 3:35 pm
date updated: Tuesday, October 18th 2022, 5:12 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Game Theory III - Bayesian Games]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

![[Game Theory II - Equilibrium#Problem Formulation]]

We all know each others' costs, and we all know that we know etc. 







# Scratch

Second price auctions we did. 

First price auction. Uniformly distributed valuations on $[0,1]$.

Strategy for 1. What's the probability I win with bid x? Assume that $b(v)$ is strictly increasing for other players (this could be shown). 

It's $P(b_2, \ldots, b_{n-1} < x)$. What's the probability that $P(b_i(v_i) < x)$ for any given $i$? Rearrange the condition to say $v_i < b\inv(x)$. I know the distribution of $v_i$. 

Two ways to approach this. 
1) easier but requires guessing
2) longer no guessing

Suppose I can say that $P(1 \text{ wins with bid } x)$ = $(x/q)^{n-1}$. Then I have $\max_x EU_1 (x, v) = (v-x)(x/q)^{n-1}$. Differentiate to get $-(x/q)^{n-1} + (v-x)(n-1)(x/q)^{n-2}/q = 0$. 
$x = v/[n/(n-1)]$


If everyone else is playing a linear strategy, I want to play one too. I don't care about their coefficients, incidentally. So this looks like a great equilibrium. 


### Generalized

First price auction: $v_i \sim F()$ on $\R+$. $F$ differentiable and $n$ arbitrary. Assume $b(v)$ is increasing (strictly). 

$$EU = \max_x (v-x)F[b\inv(x)]^{n-1}$$ I also need to find that $b(v) = x$, since this should be optimal for everyone. 
$$\begin{align}
0 &= (v-x)(n-1)f[b\inv(x)]^{n-2}[1/b'(b \inv(x))] - F[b\inv(x)]^{n-1}\\
F[b\inv(x)]^{n-1} &= (v-x)(n-1)F[b\inv(x)]^{n-2}f[b\inv(x)][1/b'(b \inv(x))]\\
F[v]^{n-1} &= (v-b(v))(n-1)F[v]^{n-2}f[v][1/b'(v)]\\
\end{align}$$

reference slides for the rest

there is some integral that comes out to define $b(v)$ as the expected value of the second highest valuation given my valuation, conditioning on my being the highest. 


--- end of midterm content ---



We hav enormal form game: $<N,S,U>$. 

Now we allow for sequenced play. Create the extensive form game.

Example

![[Game Theory III - Bayesian Games 2022-10-18 17.10.03.excalidraw|300]]

two players make choices in sequence, and the choice set depends on prior choices of self/others. The end states are called 'terminal history'


New game: 

![[Game Theory III - Bayesian Games 2022-10-18 17.13.17.excalidraw|300]]

children fighting in sandbox - a nice toy. do i take it? Will the toy's owner fight me? fighting is strictly dominated, conditional on my taking the toy? so I should take it. this is a normal formization type of result
but another NE result is: don't take (player 1 believes player 2 will fight, so doesn't take)


Need another criterion to rule that out: don't include anticipation of non credible actions. this gets rid of (take, fight) as a strategy. 

Two related concepts:
- backwards induction
- subgame perfect equilibria


A strategy in this game is how you would play in each node you would possibly get to. 
so an equilibrium is the entire result of the backward induction. 