---
aliases:
creation date: Friday, September 2nd 2022, 5:09 pm
date updated: Sunday, September 4th 2022, 7:43 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/stats/theory'
- '#topics/methods'
---

# [[Econometrics I - Foundations of Probability]]

## Basic Concepts

An event is some subset of the possible outcomes. 

What is the probability of an event? There are many definitions, which are often unsatisfactory. We will not commit to one, but we will give axioms that create some consistency. 

The most common definition is the <font color=gree>frequentist</font>. In this case, probability is the *relative* frequency of an outcome when an experiment is repeated many times, in the limit. 
- But what does it mean to repeat an experiment? We need to invoke some idea of independence of successive trials. Why bring another concept into it?
- More troublingly, we want to talk about probability for events without repeated experiments. It would be nice to set up our probability definitions without recourse to multiverse theory. 

There is also a <font color=gree>subjectivist</font> approach: each person has their own definitions for whatever. 

### Formal Definitons

- We'll start formalizing with the <font color=gree>outcome space</font>. The outcome space - sometimes called the *universal set* - is written $\Omega$. It contains elements $\omega$ which represent all possible outcomes. 
	- This can include things that never happen! 
	- If flipping a coin, our outcome space could be heads or tails - or heads, tails, and the coin is abducted by passing aliens.
- An <font color=gree>event</font> $A$ is some subset of $\Omega$ - a collection of $\omega$s. $A$ can be the null set. 
- $A^c$ is the complement of $A$, $\{\omega \in \Omega : \omega \notin A \}$. 
	- The complement is defined relative to $\Omega$. So the complement of "rolling a 1 or a 2 on a die" could be "rolling 3/4/5/6", if $\Omega$ is 'what can happen when we roll a dice'. But it could include many more things if $\Omega$ is "things that can happen on a craps table". 
- We can define the <font color=gree>union</font> $A \cup B$ as 'all outcomes in either $A$ or $B$; we can also write $\bigcup_{j=1}^J A_j$ for a sequence of sets. 
- Similarly with the <font color=gree>intersection</font> $A \cap B$, and $\bigcap_{j=1}^J A_j$. 
- <font color=gree>De Morgan's Laws</font> are direct consequences of the above definitions. 
	- $(\bigcup A_j)^c = \bigcap A_j^c$
	- $(\bigcap A_j)^c = \bigcup A_j^c$

```ad-info
title: De Morgan's Laws in Logic

It might be helpful to consider the analogous applications of De Morgan's Laws in formal logic

```
