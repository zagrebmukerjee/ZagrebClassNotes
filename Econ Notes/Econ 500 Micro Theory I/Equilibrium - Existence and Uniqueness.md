---
aliases: 
tags: 
creation date: Wednesday, November 16th 2022, 10:02 am
date updated: Wednesday, November 16th 2022, 10:47 am
---

Use BFPT to demonstrate the existence of equilibria

Next best thing: locally unique. 

example: excess demand crosses $0$ 3 times (odd # of times)
can demonstrate that at least in some neighborhood of $p^*$ there is no other WE. 
- Why is locally unique a desirable thing? locally nonunique - intuitively is sort of like tangency of curve to axis. But maybe a tiny lil tax will still destroy equilibrium entirely
- we need a theory now about adjustments. what happens when we depart from equilibrium. but theory is not very good at the moment

local uniqueness is about slope of excess demand in relation to x axis. 
- first dimension case: is derivative. 
- $z$ is $x - \omega$, so if $x$ is differentiable so is $z$. 
	- chapter 3 continuity and differentiablility of marshallian demand


so we are looking at $z(p) = x(p, p\omega)$, noting that $p$ enters into here twice. 

we need some assumptions on $u$ (lots!) so $z$ is continuously differentiable
also fix $p_l = 1$, and now $p$ is dimension $l-1$. and so we also need only $\hat z(p)$ which gives us the last good's excess demand with Walras' law. $D\hat z$ is an $L -1 \times L - 1$ matrix - we can say $D\hat z\big|_p$ for this matrix evaluated at $p$ 

An equilibrium price is regular if the determinant of $D\hat z \big|_p$ is nonzero. If the matrix has full rank
econmy is regular if all eqm prices are regular. (vacuously true if $\nexists$ equilibrium)

A few theorems that require regularity. 

### Theorem 1

If $p$ is a regular equilibrium price, then $p$ is locally unique: there exists neighborhood of $p$ st $p$ is the unique eqm px in that neighborhood
If economy is regular, there are only finitely many equilibria


we are back into implicit function theorem world [[Implicit Function Theorem]]

If determinant $\neq 0$ there exists a neighborhood $U$ of $p^*$ and neighborhood $V$ of $0$ and a function $h: V \to U$; $h$ is a bijection, and $\forall u \in U, u = h(\hat z(u))$, and for all $v \in V$, $v = \hat z (h(v))$. ie. $h$ is a local inverse of $\hat z$. 

$p^* = h(\hat z (p^*)) = h(0)$. Suppose $p \in U$ is eqm; then $\hat z(p) = 0$; so $p = h(0)$; but since $h$ bijective, this means $p = p^*$. if $p \in U$, $\hat z(p) = 0$, then $p = p^*$. 
Let $E = \{ p \in \R^{L-1}_{++}\big| \hat z(p) = 0 \}$. Then each $p \in E$ is locally unique. but I also need finiteness. 

First start with compactness of $E$. $E$ is clearly closed b/c of local uniqueness. 
boundedness. If $\hat z(p) = 0$ then $\exists r$ such that $\forall l$, $r\inv < p_l < r$. (if this were false, a price sequence with arbitrarily large prices could converge to $0$ but we demonstrated that px $\to 0$ means divergent excess demand).
in fact I can say that for all $p$s, there is one $r$ such that this is true (it's just the outer limit of all the $r$s).
So $E$ is bounded

closed and bounded means $E$ is compact 
For every $p$ there is open ball $U(p)$ around it. 
the set of $U(p)$ is an open cover of $E$; therefore I have a finite subcover 
which means there are only finitely many $U(p)$. 
So $E$ is finite. 


How do I know that tangency of $\hat z$ to $0$ is coincidental tho? Maybe it happens all the time???


a bunch of proofs here with SHT that are not that illuminating
one that builds on 'Transversality Theorem' (from Mas Collell)

Suppose $f: \R^N \to \R^M$. $f(x) = 0$; this is $M$ eqns with $N$ unknowns. Assume $f$ is $C1$. The system $f(x)$ is regular if $f(x) = 0$ implies that $\text{rank}(Df\big|_x) = M$. 
If $N >M$ we think we can solve this with many solutions? but this requires conditions... eg. linear independence. When $N<M$ we think that in general, not soluble. In that case, rank is at most $N$, so condition is not satisfiable. though observe if $N<M$ there may just be no roots - so $f(x) 0$ is regular if $\nexists x | f(x) = 0$. 




Suppose we have an irregular economy. i want to argue that most functions that I draw are not like that? but how do I argue that

vector of endowments is an object in $\R^{LI}$. so I can say if, fixing preferences, endowments are randomly distributed according to any density, 

we cd do this with production also but it's more annoying?



#### Transversality Theorem

Suppose  $f(x, q) = 0$, and $x, q$ is $N \times S$, implies that rank of $Df\big|_{x,q} = M$. 
Then for almost all $q$,  rank of $D_x f\big|_(x,q) = M$ whenever $f(x,q) = 0$. 

ie. I have some system $Df$ with $M$ rows and $N$ columns. I can make it easier by looking at the derivative of $f$ with respect to $q,x$ and this matrix can get me much more space $M \times N + S$. in which to search for independent columns. 

in our case, $S$ is huge - $\omega$ is $i$ vectors of $l$ space. 


so now I have some set of perturbations such that $p\Delta\omega_1 = 0$; a net $0$ change in income; so $\hat z(p) =0$ with $p >> 0$. So $\Delta\omega_{L} = -p_l\sum_{i=1}^{L-1}\Delta\omega_l$. 
$D_{\omega_1} x_1(p, p\omega_1) d\omega_1 = 0$. But with very little restriction on $\omega$. I haven't changed anyone's excess demand or anyone else's endowment. 
$d \hat z_1$ or $D_{\omega_1} \hat z_1(p) \Delta\omega_1$, resultant differential change in $\hat z$ is just $-\Delta \hat\omega_1$. These are linearly independent, image is $L - 1$ dimension. 
so dim(image($D_{\omega_1}\hat z(p)$)) is $L -1$. So rank of $D_{p,\omega} \hat z \big|_{p,w} = L-1$. 