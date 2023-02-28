---
aliases:
creation date: Sunday, February 26th 2023, 12:57 pm
date updated: Monday, February 27th 2023, 8:50 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[🚧Game Theory 501 VI - Imperfect Information]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


## Representing Uncertainty

### Incomplete Information

The representation of games with incomplete information can be challenging. Suppose the following transformation of the Battle of the Sexes: 

|     | P               | G     |
| --- | --------------- | ----- |
| P   | $2 + \theta_1, 1$ | $0,0$ |
| G   | $0,0$           | $1, 2 + \theta_2$      |


Here, instead of static preferences, we've said each player has some degree of preference for $P$ vs $G$ that's unknown to the other player. So in order to make a decision, Player $1$ needs to consider their own preference. But they also need to form some belief about Player 2's preference. For instance, if they know $\theta_1 = 1$ but believe $\theta_2 = 5$ then they will think it much more likely that Player $2$ will choose $G$.

But to turn this into a strategy, Player $1$ also needs to think about Player $2$'s expectations about Player $1$'s preference; even if $\theta_2 = 5$, if Player $2$ thinks $\theta_1 = 10$ then they will believe it more likely that Player $1$ will play $P$; by ignoring that possibility, Player $1$ would forgo a potential gain. 

But then Player $1$ needs to understand that Player $2$ understands the above; and so Player $2$ will incorporate some guess about Player $1$'s guess about Player $2$'s guess about Player $1$. We can very quickly enter some sort of problem of infinite regress.

### Imperfect Information

A framework to analyze such games was developed by Harsanyi (with no particular basis in fact, but an eye to tractability). One may suppose that the game has a specific type of incomplete information: Nature draws $\theta_1, \theta_2$ from a commonly known distribution. So players have *common priors* and then can anchor their guesses about others' strategies in those priors. 

Suppose $\theta_i$ is drawn from $\text{Unif}(0, \epsilon_i)$, and both players know that. Player $1$ doesn't know what Player $2$ will do, but knows that it will be increasing in $\theta_2$. Therefore, Player $2$'s choice can be represented as a cutoff: if $\theta_2 > c_2$, $s_2 = G$.  

Then we can reason about Player $1$'s choice by the same monotonicity logic, ie. finding $c_1$ such that $\theta_1 > c_1 \implies s_1 = P$. It follows that for $\theta_1 = c_1$, Player $1$ is indifferent between $P$ and $G$.

$$\begin{align}
E[u_1(P)] &= E[u_1(G)]\\
(2 + \theta_1) P( \theta_2 < c_2) &= (1)P(\theta_2 > c_2)\\
(2 + \theta_1) \frac{c_2}{\epsilon_2} &= 1 - \frac{c_2}{\epsilon_2}\\
(2 + \theta_1) c_2 &= \epsilon_2 - c_2\\
3c_2 + c_1c_2  &= \epsilon_2 \\
c_1(c_2) &= \epsilon_2/c_2 - 3\\
c_1^* &=  \epsilon_2/c_2(c_1^*) - 3\\
&=  \epsilon_2/(\epsilon_1/c_1 -3) - 3\\
c_1 + 3 &= \frac{\epsilon_2c_1}{\epsilon_1 -3c_1} \\
0&=(c_1 + 3)(\epsilon_1 - 3c_1) - \epsilon_2 c_1 \\
&=c_1 \epsilon_1  + 3\epsilon_1 - 3c_1^2 - 9c_1 - \epsilon_2 c_1 \\
&= -3c_1^2 + c_1(\epsilon_1 - \epsilon_2 - 9) + 3 \epsilon_1\\
&= 3c_1^2 - c_1(\epsilon_1 - \epsilon_2 - 9) - 3 \epsilon_1\\
\end{align}$$

For simplicity, solve for the special case where $\epsilon_1 = \epsilon_2$. Then use the quadratic formula: 

$$\begin{align}
c_1 &= \frac{3 + \sqrt{9 +4 \epsilon}}{2}
\end{align}$$

### Public Goods Provision

Two players simultaneously decide whether to pay for a public good. If at least one pays, both accrue a benefit of $1$. If none do, $0$. Cost of contributing is $c_i$. $c$ is drawn fro continuous and strictly increasing cdf $F$ on $[\underline c, \overline c]$. 

A strategy, then, is a map from $\text{supp} \; c$ into $\{0,1\}$. Player $i$ maximizes utility: 

$$ u_i = \max_j s_j - c_i s_i$$
A best response is a function that, for any $c_i$, maximizes $E[u_(c_i|s_{-i})]$ . So a BNE has each player playing $s_i^*$ that maximizes $E[u(s_i, s_{-i}^*, c_i]$. $c_j$ doesn't directly matter for this maximization problem, but it'll enter into others' calculations. 

Suppose I am player $i$. Then there's an equilibrium probability $z_j$ that $j$ contributes. So I will contribute if $c_i < 1- z_j$; ie if it's worth it to me to insure against the other guy not contributing. In other words, there's another cutoff strategy: Player $i$ contributes if $c_i \in [\underline c, c^*_i]$. 

So Player $1$ knows that $z_j = F(c_j^*)$; the probability another will contribute is the probability that their cost is low enough. Then I can solve the above, again using the idea that at $c_i^*$ I am indifferent:

$$\begin{align}
E[u(s_i = 0, c_i^*)] &= E[u(s_i = 1, c_i^*)]\\
1 - c_i^* &= z_j\\
c_i^* &= 1-F(c_j^*)\\
&= 1-F(1 - F(c_i^*))\\
\end{align}$$

Symmetry lets you say that $c_i^* = c_j^* = c^*$; and then for a given $F$, the above can be solved. 


## Purification

Theorem (Harsanyi): Every mixed strategy NE in a perfect-information game can be represented as the limit of a sequence of Bayesian NEs in an imperfect information game.


### Example 1
#### Perfect Information Game

|      | Left   | Right  |
| ---- | ------ | ------ |
| Up   | $0,0$  | $0,-1$ |
| Down | $-1,0$ | $3,5$  |

PSNE exists: $D,R$. But an MSNE also exists. 

Indifference conditions for Player $1$: 

$$\begin{align}
0 &= -p_L + 3(1-p_L)\\
p_L &= 3/4\\
\end{align}$$
Player $2$: 


$$\begin{align}
0 &= -p_U + 5(1- p_U)\\
p_U &= 5/6\\
\end{align}$$


#### Perturbed Game
Introduce some perturbation based on a type. Suppose $\theta_i \sim \text{Unif}[-1,1]$, fix $\epsilon > 0$, and let the payoffs be 


|      | Left   | Right  |
| ---- | ------ | ------ |
| Up   | $\epsilon \theta_1,\epsilon \theta_2$  | $\epsilon \theta_1,-1$ |
| Down | $-1,\epsilon \theta_2$ | $3,5$  |

Still have $E[\epsilon \theta_1] = 0$. Now, solve for cut-point Bayesian Nash Equilibrium. 

Player $1$ plays $U$ if $\theta_1 > c_1$, $D$ otherwise; and Player $2$ playes $L$ if $\theta_2 > c_2$, $R$ otherwise.  Start with Player $1$. 

$$\begin{align}
E[u(U)] &= E[u(D)]\\ 
\epsilon c_1  &= -p_L + 3(1- p_L)\\
c_1 &= \frac{3 - 4p_L}{\epsilon}\\
&= \frac{3 - 4P(\theta_2 > c_2)}{\epsilon}\\
&= \frac{3 - 2(1 - c_2)}{\epsilon}\\
&= \frac{2c_2 + 1}{\epsilon}\\
\end{align}$$





$$\begin{align}
E[u(L)] &= E[u(R)]\\ 
\epsilon c_2  &= -1(P(s_1 = U)) + 5 P(s_1 = D)\\
&= -(1-c_1)/2 + 5(c_1 + 1)/2\\
&= -1/2+c_1/2 + 5c_1/2 + 5/2\\
c_2 &= (3c_1 + 2)/\epsilon\\
&= \frac{3((2 c_2 + 1)/\epsilon) + 2}{\epsilon}\\
&= \frac{6 c_2/\epsilon + 3/\epsilon + 2}{\epsilon}\\
&= \frac{6 c_2 + 3 + 2\epsilon}{\epsilon^2}\\
c_2 &= \frac{3 + 2 \epsilon}{\epsilon^2  -6 }\\
\end{align}$$

So in the limit, $c_2 = -1/2$; probability $\theta_2 > c_2 = 3/4$, so $p_L = 3/4$. 




### Example 2 (Inspection Game)

#### Perfect Information Game

An agent chooses 'Work' or 'Shirk'. Working costs $c$. The principal has hired the agent to do work, and has to choose to inspect or not; inspection costs $h$. If the worker works, the principal gets $v$; the agent gets paid $w$ unless they are caught shirking. Then

|       | Inspect      | Don't      |
| ----- | ------------ | ---------- |
| Shirk | $0, -h$      | $w, -w$     |
| Work  | $w - c, v-h-w$ | $w - c, v-w$ |


Suppose $w > c$ for interestingness - otherwise, shirk would be dominant strategy. Suppose also that $h < w$; otherwise never would inspect. 

There's no pure strategy equilibrium: agent's BR to inspecting is to work, and to non-inspecting to shirk. Principal's BR to shirk is to inspect, and to work is to not inspect. So mixture is required. Let $p$ be the probability of inspection, $q$ of shirking.

Agent's indifference condition.
$$\begin{align}
E[u(S)] &= E[u(W)]\\
w(1-p) &= w-c\\
1- p &= 1 - c/w\\
p &= c/w\\
\end{align}$$
Principal's:

$$\begin{align}
E[u(I)] &= E[u(D)]\\
q(-h) + (1-q)(v - h - w) &= q(-w) + (1-q)(v-w)\\
q(w - h) &= (1-q)(v - w - v + h + w)\\
q(w - h) &= (1-q)(h)\\
qw - qh &= h - qh\\
q &= h/w\\
\end{align}$$
#### Perturbation

Perturb $c$ and $h$; draw $\theta_A, \theta_P$ from $\text{Unif}[-1/2,1/2]$, and let the game be: 

|       | Inspect      | Don't      |
| ----- | ------------ | ---------- |
| Shirk | $0, -h - \epsilon \theta_P$      | $w, -w$     |
| Work  | $w - c - \epsilon \theta_A, v-h- \epsilon \theta_P-w$ | $w - c- \epsilon \theta_A, v-w$ |

The agent will shirk for sufficiently large $\theta_A$ and work otherwise; the principal will not inspect for sufficiently large $\theta_P$. Let the cutpoints be $c_A, c_P$. 

Solve for $c_A$ as the value that makes the agent indifferent; let probabilities be $p, q$ as before. 

$$\begin{align}
E[u(S)] &= E[u(W)]\\
w(1-p) &= w-c -\epsilon c_A\\
w-wp &= w-c -c_A\\
c_A &= \frac{wp - c}{\epsilon}\\
&= \frac{wP(\theta_P>c_P) - c}{\epsilon}\\
&= \frac{w(1/2- c_P) - c}{\epsilon}\\
\end{align}$$

For $c_P$: 
$$\begin{align}
E[u(I)] &= E[u(D)]\\
q(-h - \epsilon c_P) + (1-q)(v - h - \epsilon c_P- w) &= q(-w) + (1-q)(v-w)\\
q( w-h - \epsilon c_P)  &= (1-q)(v-w - (v - h - \epsilon c_P- w))\\
q( w-h - \epsilon c_P)  &= (1-q)(h + \epsilon c_P)\\
qw-qh - q\epsilon c_P  &= (h + \epsilon c_P) - qh - q\epsilon c_P\\
qw&= h + \epsilon c_P\\
c_P &= \frac{wq -h}{\epsilon}\\
&= \frac{wP(\theta_A > c_A) -h}{\epsilon}\\
&= \frac{w(1/2  - c_A) -h}{\epsilon}
\end{align}$$


Then plug in the above for $c_A$: 

$$\begin{align}
c_P &= \frac{w(1/2  - \frac{w(1/2- c_P) - c}{\epsilon}) -h}{\epsilon}\\
&= \frac{w\epsilon(1/2  - \frac{w/2- wc_P - c}{\epsilon}) -h\epsilon}{\epsilon^2}\\
&= \frac{w\epsilon/2  - w\epsilon\frac{w/2- wc_P - c}{\epsilon}) -h\epsilon}{\epsilon^2}\\
\end{align}$$
