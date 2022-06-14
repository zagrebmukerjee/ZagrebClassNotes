---
aliases:
creation date: 2022-06-10 19:16
date updated: Tuesday, June 14th 2022, 4:10 pm

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

Define $\bar E'$ as  the limit points of $\bar{E}$, and consider some point $p \in \bar{E}'$. Every neighborhood $N$ around $p$ contains an element of $\bar{E}$, which means $N$ contains either an element of $E$ or of $E'$. Suppose $N$ contains an element of $E'$; then by the same logic as in step 1 it contains an element of $E$ as well. Therefore every $N$ contains an element of $E$, meaning $p$ is a limit point of $E$. 

So since $E' \subset \bar{E}'$, and $\bar{E}' \subset E'$, they are the same. 


c) No. Consider the set of reciprocals of the integers, $E = \{1/1, 1/2, 1/3, \ldots, 1/n \}$. It follows that $E' = \{0\}$. But since $E'$ has only one element, it has no limit points. 

7) ![[Pasted image 20220613183236.png]]
8) a) Yes. Consider any point $p \in E$. Since $E$ is open, $p$ is an interior point; so there exists an $r$ such that $N_r(P) \subset E$. Any neighborhood of $p$ has radius either $>r$ or $\leq r$. If less than or equal, that neighborhood is a subset of $N_r(p)$, and so is a subset of $E$, and contains points in $E$. If greater, that neighborhood contains $N_r(p)$ and thus contains points in $E$. So every neighborhood of $p$ contains points in $E$, meaning $p$ is a limit point. This is not true for closed sets; consider the set ${0}$. 


9) ![[Pasted image 20220613183248.png]]
10) ![[Pasted image 20220613183257.png]]
11) ![[Pasted image 20220613183305.png]]
12) ![[Pasted image 20220613183317.png]]
14) ![[Pasted image 20220613183323.png]]

Consider the progression of intervals $(1/n, 1)$ for $n \in \mathbb{Z}$. 
- This covers $(0,1$): Suppose $0 \leq x \leq 1$. There is an integer $m$ such that $m > 1/x$. It follows that $1/m < x$; thus, $x \in (1/m, 1)$. 
- This has no finite subcover: Suppose there is a finite subcover. Then that subcover has a least element, $1/n_{min}$. But we know that  $1/(n_{min} + 1) >0$; and $1/(n_{min} + 1) < 1/n_{min}$, so $1/(n_{min} + 1) \notin (1/n_{min}, 1)$. Thus the finite subcover is not a cover. 

15) ![[Pasted image 20220613184303.png]]
16
17
18
19) ![[Pasted image 20220613184319.png]]
22) ![[Pasted image 20220613184329.png]]
24) ![[Pasted image 20220613184337.png]]
25
