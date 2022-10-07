---
aliases:
- 'Cauchy-Schwarz Inequality'
- 'Cauchy-Bunyakowsky-Schwarz Inequality'
- 'CBS Inequality'
- "Holder's Inequality"
- "Lyapunov's Inequality" 
- "Minkowski's Inequality"

creation date: Tuesday, October 4th 2022, 11:57 am
date updated: Friday, October 7th 2022, 12:29 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Econometrics VI - Inequalities and Important Results]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

Not to be confused with [[Inequality]]

![[Markov's and Chebyshev's Inequalities#Markov's Inequality]]

![[Markov's and Chebyshev's Inequalities#Chebyshev's Inequality]]

### Cauchy-Bunyakovsky-Schwarz Inequality
#### Expected Value Form:

For any RVs $X, Y$ we have 

$$E|XY| \leq E|X^2|^{1/2}E|Y^2|^{1/2}$$

Proof:

Let $a = EXY/EX^2$. Then square both sides: 

$$\begin{align}
Y &= (Y - aX) + aX\\
Y^2 &= (Y - aX)^2 +(aX)^2 + 2 (Y-aX)aX\\
E(Y^2) &= E(Y - aX)^2 +E(aX)^2 + 2 E[(Y-aX)aX]\\
2 E[(Y-aX)aX] &= E[aXY - a^2X^2]\\
&= EYaX - Ea^2X^2\\
&= EXY\frac{EXY}{EX^2} - \frac{EXY^2}{EX^2}\\
&= 0\\
E(Y^2) &= E(Y - aX)^2 +E(aX^2) \\
E(Y^2) \geq E(a^2X^2)\\
&\geq \frac{EXY^2}{EX^4}EX^2\\
&\geq \frac{EXY^2}{EX^2}\\
E(Y^2)E(X^2) &\geq E(XY)^2\\
E|Y|E|X| &\geq E|XY|\\
\end{align}$$


#### Vector Form
$$ |a'b| \leq (a'a)^{1/2}(b'b)^{1/2}$$
or
$$ |a'b| \leq \sqrt{||a||||b||}$$
#### Function Form

$$\left| \int g(x)h(x) f_X(x) dx \right| \leq\left(\int g^2(x)f_X(x)dx\right)^{1/2}\left(\int h^2(x)f_X(x)dx \right)^{1/2}$$
![[Jensen's inequality#Jensen's Inequality]]

### Holder's Inequality

Holder's inequality generalizes the [[#Cauchy-Bunyakovsky-Schwarz Inequality]]. Let $p, q \geq 1$ and $\frac{1}{p} + \frac{1}{q} = 1$. 

For any two random variables:

$$E(|XY|) = (E|X^p|)^{1/p}(E|X^q|)^{1/q}$$
So the CBS is the particular case when $p = q = 2$. 
Note that this doesn't require finite moments? but it's pretty dang useless without it. 

Proof: not instructive

We can also define an <font color=gree>L<sup>p</sup>-Norm</font> as $||x

### 