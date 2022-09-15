---
aliases:
creation date: Wednesday, September 14th 2022, 6:00 pm
date updated: Wednesday, September 14th 2022, 6:34 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#types/classes/practice'
---

# [[Metrics Section 9-14]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


2015 midterm. Let $P$ be a probability distr on $\Omega, \mathcal F$ for $B \in \mathcal F$ with $P(B) > 0$ show $P(A|B)$ for $A \in \mathcal F$ is a proper probability distribution. 

It has to satisfy three criteria. 
1) PR nonnegative. $P(A|B) = P(A \cap B)/P(B)$. We know $P(B) >0$; we know $P(A\cap B) \geq 0$; so result nonnegative
2) PR of the outcome space is $1$. This is $P(\Omega|B)$, which is $P(\Omega \cap B)/P(B) = P(B)/P(B) = 1$. 
3) Countable additivity: Suppose countable disjoint $A_i$. $P(\bigcup_{i \in \mathbb Z} A_i|B)$ is the same as $P(\bigcup A_i \cap B)/P(B)$. Since intersection distributes over union we have this is the same as $P(\bigcup (A_i \cap B))/P(B) = \sum P(A|B)$
4) 


2014 midterm. Let $A_1, \ldots, A_k$ be events. Show that $P(\bigcup A_i) = 1 - P(\bigcap A^c)$. We proceed by applications of De Morgan's law. This tells me that $P(\bigcup A_i)^c = P(\bigcap A^c)$. And we know that $P(B^c) = 1 - P(B)$. So it follows that $1 - P(\bigcap A^c) = 1P(\bigcup A_i)^c = P(\bigcup A_i)$.    



2016 midterm 
Show that $P(A \cup B) = P(A) + P(B) - P(A \cap B)$

Define 'set-minus', $\setminus$: $X \setminus Y = \{ x \in X : x \notin Y \}$. (This would be the same as $X \cap Y^c$). 

We know that $P(A) = P(A \setminus (A\cap B)) + P(A \cap B)$, since these are disjoint and their union is $A$. So we know that $P(A \setminus (A \cap B)) = P(A) - P(A \cap B)$. We can also write $ P(B \setminus (A \cap B)) = P(B) - P(A \cap B)$. We know that $A \setminus (A \cap B), A \cap B$, and $B \setminus (A \cap B)$ are mutually disjoint. We know their union is $A \cup B$. So we can write: 

$$\begin{align}
P(A \cup B) &= P(A \setminus (A \cap B) + P(B \setminus (A \cap B)) + P(A \cap B) \\
&= (P(A) - P(A \cap B)) + (P(B) - P(A \cap B)) + P(A \cap B) \\
&= P(A) + P(B) - P(A \cap B) \\
\end{align}$$

Strategy: prove the lemmas etc after each class without looking. 