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

a) Suppose a point $p$ that is not in $E



For $p \in E'$, suppose there is a neighborhood $N$ of radius $r$ around $p$ that contains no elements of $E'$. Let $q$ be any point in $N$; $q$ then cannot be a limit point of $E$, and so there is some neighborhood $N_q$ around $q$ that contains no points of $E$. But since we haven't specified $q$, that means we can cover $N$ with neighborhoods that contain no points of $E$, which in turn means that $N$ contains no points in $E$. But then $p$ cannot be a limit point. 



b) 

7) ![[Pasted image 20220613183236.png]]
8) 
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
