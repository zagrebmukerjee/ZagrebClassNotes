---
aliases:
creation date: 2022-06-10 19:16
date updated: Wednesday, June 15th 2022, 12:45 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/math/analysis'
- '#status/🚧'
---

# [[Rudin Ch2 and Exercises]]
[[Real Analysis Su and Rudin]]

## Notes

Metric space = a set + a distance fn
Distance properties:
1) non-negativity (positivity if $p /neq q$
2) symmetry
3) triangle inequality 


open balls - one of which is a neighborhood - can write $N_r(x)$ is $\{ p | d(p,x)<r \}$ (note - strictly less than. if $\leq$ then closed ball)


- Limit point: $p$ is limit pt of set $E$ if *every* neighborhood of $p$ contains some $q$ such that $q \neq p$ and $q \in E$.
- Isolated point: $p \in E$ but $p$ is not a limit point
- Interior point: $p \in E$ and there exists a ball $N_r(p)$ that is a subset of $E$. 

- Set is open if every point is an interior point. Intuitively that means you can sort of jiggle anything around and it'll remain in the set.
- Closed set 



## Exercises

2) ![[Pasted image 20220613183158.png]]
Every algebraic number can be written as $n+1$ integers $(a_0, \ldots, a_n)$. We know from the hint that there is a finite number of these for every integer; it follows that there's a finite number for each length $n$, since no finite set has infinite subsets. So we have a finite number of finite sets. A parallel argument to the $\mathbb Z \to \mathbb Z^n$ thence applies. 

3) ![[Pasted image 20220613183215.png]]
It follows from the countability of the algebraics.

4) Rationals are countable, reals are uncountable, so irrationals must be uncountable

5) $$ \{1/2, 1/3, \ldots, 1/n\} \cup \{3/2, 4/3, \ldots, (n+1)/n\} \cup \{5/2, 7/3, \ldots, (2n + 1)/n\} $$
This set has $0$ as a limit point, as well as $1$ and $2$. 

6) ![[Pasted image 20220613183227.png]]

a) Suppose a point $p$ is a limit point of $E'$. Consider some neightborhood $N$ around $p$ with radius $r$. This must contain an element of $E'$; call it $q$. $d(q,p) < r$, so let $s = [r - d(q,p)]/2$, and draw a neighborhood $N'$ of radius $s$ around $q$. 

Every point in $N'$ has distance from $q$ of at most $s$, which means its distance from $p$ is at most $d(q,p) + s < r$. So $N' \subset N$. But since $q \in E'$ there is some element of $N'$ that is in $E$. So any neighborhood $N$ around $p$ contains an element of $E$, and so $p$ must be a limit point of $E$; so every limit point of $E'$ is in $E'$, and thus $E'$ is closed. 

b) First, consider $p \in E'$. Every neighborhood around $p$ contains an element of $E$ by construction, so it contains an element of $\bar{E}$; so every limit point of $E$ is a limit point of $\bar{E}$. 

Define $\bar E'$ as the limit points of $\bar{E}$, and consider some point $p \in \bar{E}'$. Every neighborhood $N$ around $p$ contains an element of $\bar{E}$, which means $N$ contains either an element of $E$ or of $E'$. Suppose $N$ contains an element of $E'$; then by the same logic as in step 1 it contains an element of $E$ as well. Therefore every $N$ contains an element of $E$, meaning $p$ is a limit point of $E$. 

So since $E' \subset \bar{E}'$, and $\bar{E}' \subset E'$, they are the same. 


c) No. Consider the set of reciprocals of the integers, $E = \{1/1, 1/2, 1/3, \ldots, 1/n \}$. It follows that $E' = \{0\}$. But since $E'$ has only one element, it has no limit points. 

7) ![[Pasted image 20220613183236.png]]
8) a) Yes. Consider any point $p \in E$. Since $E$ is open, $p$ is an interior point; so there exists an $r$ such that $N_r(P) \subset E$. Any neighborhood of $p$ has radius either $>r$ or $\leq r$. If less than or equal, that neighborhood is a subset of $N_r(p)$, and so is a subset of $E$, and contains points in $E$. If greater, that neighborhood contains $N_r(p)$ and thus contains points in $E$. So every neighborhood of $p$ contains points in $E$, meaning $p$ is a limit point. This is not true for closed sets; consider the set ${0}$. 


9) ![[Pasted image 20220613183248.png]]
a) Choose a point $p$ in $E^\circ$. 
- For some radius $r_0$, since $p$ is in the interior of $E$, $N_r(p) \subset E$ when $r < r_0$. 
- Suppose $p$ is not in the interior of $E^\circ$. Choose $r' < r_0$, so $N_{r'}(p) \subset E$. By supposition, $N_{r'}(p)$ contains some point $q \notin E^\circ$. But then $q$ cannot be in the interior of $E$, so every neighborhood around $q$ contains something not in $E$, which means that $N_{r'}(p)$ contains a point not in $E$, contradicting the supposition. 
- Thus every point in $E^\circ$ is an interior point of $E^\circ$, meaning $E^\circ$ is open. 

b) If $E^\circ = E$ then openness follows from a). In the other direction, we want to show that openness implies $E^\circ = E$. Suppose $E$ is open. Then every point in $E$ is an interior point of $E$; it follow that every point is in $E^\circ$ meaning that $E^\circ = E$. 

c) $G$ being open implies that every point in $G$ is an interior point of $G$; which means for any $p \in G$ there is some $N(p) \subset G$, which means that that $N(p) \subset E$, and so $p$ is in the interior of $E$; thus $G \subset E^\circ$. 

d) every point in $E^\circ$ has a neighborhood containing only points in $E$, meaning it contains no points in $E^c$. So no points in $E^\circ$ are limit points of $E^c$. #status/section/🚧 

e)f) The rationals have a closure that is $\R$ and no interior. 


10) ![[Pasted image 20220613183257.png]]
The discrete metric!

Has non-negativity. $d(p,q) = 0$ iff $p=q$. Obviously transitive. 

The triangle inequality becomes the triangle equality for $r \notin \{p,q\}$. Otherwise:

$$d(p,q) \leq d(p,r) + d(r,q)  \to 1 \leq 2$$
Any subsets are open. For any subset $E$ containing point $p$ it is possible to draw a ball of radius $r < 1$ around $p$ that contains $p$, and thus only elements of $E$. Thus any subset, since it is the complement of some other subset, is also closed.

Any finite subset is compact. Every open cover must contain some ball around each point, and that finite set of balls can be an open subcover. 

11) ![[Pasted image 20220613183305.png]]
Note: all have non-negativity. 
$d_4$ lacks the symmetry property. Consider $a = 0$, $b = 1$. $d_4(a,b) = |0-2| = 2$, but $d_4(b,a) = |1-0| = 1$. 

For the others, let us test the triangle inequality:
- $d_1(p,q) \leq d_1(p,r) + d_1(r,q)$ evidently fails in the case of $p = 1$, $q = 3$, $r = 2$. $d_1(1,2) = d_1(2,3) = 1$, but $d_1(1,3) = 4$. 
- $d_2(p,q) \leq d_2(p,r) + d_2(r,q)$; We can write $r = p + a$, and $q = p + a + b$. Then $d_2(p,q) = \sqrt{|a+b|}$, $d_2(p,r) =\sqrt{|a|}$, and $d_2(r,q) = \sqrt{|b|}$. $(\sqrt{|a|} + \sqrt{|b|})^2$ = $|a| + |b| + 2\sqrt{|a||b|} \geq |a + b|$. 
- $d_3$ has the problem that $d(x,-x) = 0$ but $x \neq -x$
- $d_5$ is more fun. We can write as before:

$$\begin{align}d(p,q) \quad &? \quad d(p,r) +  d(r,q) 
\\
\frac{|a + b|}{1 + |a + b|} \quad &? \quad  \frac{|a|}{1+ |a|}+  \frac{|b|}{1+|b|} \\
\frac{|a + b|(1+|b|)(1+ |a|)}{(1 + |a + b|)(1+|b|)(1+ |a|)} \quad &? \quad  \frac{|a|(1+|b|)(1 + |a + b|)}{(1+ |a|)(1+|b|)(1 + |a + b|)}+  \frac{|b|(1+ |a|)(1 + |a + b|)}{(1+ |a|)(1+|b|)(1 + |a + b|)} \\
(|a + b|+|a + b||b|)(1+ |a|) \quad  &? \quad (|a| + 2|b||a| + |b|)(1 + |a + b|) \\
|a + b|\quad  &? \quad |a| + 2|b||a| + |b| + |b||a||a + b|    \\
0 \quad  &? \quad |a| + |b| - |a + b| + 2|b||a|  + |b||a||a + b|   \\
\end{align} $$

Since $|a| + |b| \geq |a + b|$ the triangle inequality holds.


12) ![[Pasted image 20220613183317.png]]

Any open cover $C$ of $K$ must contain all balls of some radius $r$ around the points of $K$, since the points of $K$ are interior points of $C$ by openness. Given any $r$, consider  $C'=[0, 1/m < r]$, where $m$ is an integer such that $1/m < r$. We know that all points within distance $r$ of $0$ are contained in $C$, by construction; so we know this interval is inside $C$. But the union of $C'$ and the (at most) $m-1$ balls around elements of $K$ is finite, so this is a finite subcover.

14) ![[Pasted image 20220613183323.png]]

Consider the progression of intervals $(1/n, 1)$ for $n \in \mathbb{Z}$. 
- This covers $(0,1$): Suppose $0 < x < 1$. There is an integer $m$ such that $m > 1/x$. It follows that $1/m < x$; thus, $x \in (1/m, 1)$
- This has no finite subcover: Suppose there is a finite subcover. Then that subcover has a least element which we can bound below with $1/n_{min}$. But we know that  $1/(n_{min} + 1) >0$; and $1/(n_{min} + 1) < 1/n_{min}$, so $1/(n_{min} + 1) \notin (1/n_{min}, 1)$. Thus the finite subcover is not a cover. 

15) ![[Pasted image 20220613184303.png]]
![[Pasted image 20220618213622.png]]

Suppose ${K_\alpha}$ is a collection of *closed* subsets such that every finite subcollection has a nonempty intersection. 


16
17
18 optional
19) ![[Pasted image 20220613184319.png]]

a) Recall that sets are separated if $A \cap \overline B = B \cap \overline A = \emptyset$. Suppose closed sets $A$ and $B$ are not separated. Then it follows that there is some point of $A$ in the closure of $B$ or vice versa. But every point in the closure of $B$ is in $B$. So there is some point of $A$ in $B$, meaning they are not disjoint - so the theorem follows by contrapositive. 

b) Suppose two open sets $A$ and $B$ are not separated. Then there is some point $p$ of $A$ in the closure of $B$ or vice versa. Since $p$ is in $A$, there is some neighborhood $N(p)'$of $A$ that is a subset of $A$. Since $p$ is in the closure of $B$, every neighborhood of $p$ contains some point of $B$. Specifically, $N(p)'$ contains some point of $B$, meaning that $A$ and $B$ share a point, so they are not disjoint.


22) ![[Pasted image 20220613184329.png]]

That $\mathbb Q^k$ is countable has been established. The density of the rationals in the reals is 1.20 b. So $\R^1$ is separable. 

$\R^k$ is the set of tuples $(x_1, \ldots, x_k)$ with each $x$ in $\R^1$. Suppose $p \in \R^k$ has some closest rational $q \in \mathbb Q^k$, a tuple of rationals $(q_1, \ldots, q_k).$ So for some distance $r$, $\sqrt{(x_1 - q_1)^2 + \ldots + (x_k - q_k)^2  } = r$. But by the density of $\mathbb Q^1$ in $\R^1$, we know that there exists a $q_{1}'$ such that $x_1 < q_{1}' < q_1$. So then make $q' \in \mathbb Q^k$ which is $(q_{1}', q_2, \ldots, q_k)$. It follows that $\sqrt{(x_1 - q_1')^2 + \ldots + (x_k - q_k)^2 } < r$. So any element of $\R^k$ has no closest rational, meaning that $\mathbb Q^k$ is dense in $\R^k$. Thus $\R^k$ has a dense countable subset and so is separable. 

24) ![[Pasted image 20220613184337.png]]
25
