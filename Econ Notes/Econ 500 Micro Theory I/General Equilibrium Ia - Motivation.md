---
aliases:
creation date: Saturday, October 29th 2022, 10:40 am
date updated: Sunday, November 6th 2022, 10:47 am

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
---

# [[General Equilibrium Ia - Motivation]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>
[[Econ 500 Micro Theory Index]]

## General Vs Partial Equilibrium

Previously we studied partial equilibrium. In this conception we studied the problem of an individual agent, and from that perspective we were able to exogenize several important things, most notably price. Now we are going to ask - what would happen if we try to endogenize price? Is a price not the result of endogeneous actions that determine supply and demand?

'Zooming out' to this level allows for broader conceptions of certain problems. 

## Illustrative Example

We're going to study a tax incidence case. Suppose we have $N$ towns with $N$ firms, and $M$ workers spread across these towns, with $N, M$ pretty big. The firms have a common technology $f(z)$, for labor $z$ with $f'>0$ and $f'' < 0$. The output is sold at price $1$. 

Now, what happens when a town (eg town 1) imposes some tax $t$ on its local firm?

### Partial Equilibrium

Let $w$ be the prevailing wage. Then, in the pretax case, the firm maximizes $f(z) -wz$, and from the FOC we have that $f'(z^*) = w$. Adding this up across firms, we have that $z_1 = z_2 = \ldots$, and so $z_i = M/N$; then $f'(M/N) = w$. 

Now town 1 imposes a payroll tax $t$. In effect, firm 1 now maximizes $\pi_1 = f(z) - (w+t)z$. What's the incidence of this tax? 

Firm 1's FOC is now $f'(z_1) = w + t$. The profit was $f(M/N) - f'(M/N)M/N$. Now that it's forced to produce less, from the monotonicity and concavity of $f$ we can say that Firm 1's profits fall, so the incidence of the tax is on owners of Firm 1. 

Zooming out will demonstrate that this is an erroneous conclusion. 

### General Equilbrium

Now we are going to ask what happens to all of the firms and the entire labor pool. We'll now endogenize wages as $w(t)$, the prevailing wage given the tax. Let $t$ be small ($dt$). 

Now we will look at the whole set of first-order conditions. 
$$\begin{align}
f'(z_1(t)) = w(t) + t\\
f'(z(t)) = w(t)\\
(N-1)z(t) + z_1(t) = M\\
\end{align}$$
When $t = 0$ then $z_1(t) = z(t)$, and $w(0) = M/N$. Back to our base scenario. To understand what changes, we can use the implicit function theorem to totally differentiate . First a bit of rearranging though. 

$$\begin{align}
f'(M - (N-1)z(t)) &= w(t) + t\\
-(N-1)z'(t) f''(M - (N-1)z(t)) &= w'(t) + 1\\
f'(z(t)) &= w(t)\\
z'(t)f''(z(t)) &= w'(t)\\
\end{align}$$
We can evaluate at $t = 0$. Then
$$\begin{align}
M - (N-1)z(0) &= M - (N-1)M/N\\
& = M/N\\
-(N-1)z'(0) f''(M - (N-1)z(t)) &= w'(t) + 1\\
-(N-1)z'(0) f''(M/N) &= z'(0)f''(M/N)+ 1\\
z'(0) f''(M/N) &= -1/N\\
w'(0) &= -1/N\\
\end{align}$$

Total profits are $(N-1)\pi(w(t) + \pi (w(t) + t)$. Total differentiation gives us $(N-1)\pi'(w(t))w'(t) + w'(t)\pi'(w(t) + t)$. Evaluate at $0$ to get $\pi(w(0))[(N-1)w'(0) + w'(0) + 1] = \pi(w(0))[(N-1)(-1/N) + (-1/N + 1)]$ $\pi(w(0))[(-N + 1)/N + (N-1)/N] = 0$. So profit is unchanged - the entire cost is borne by the workers. 
