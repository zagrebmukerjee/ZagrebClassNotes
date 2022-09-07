---
aliases:
creation date: Thursday, September 1st 2022, 5:23 pm
date updated: Wednesday, September 7th 2022, 3:42 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#topics/econ/theory/micro'
- '#status/🚧'
---

# [[Micro Theory I - Representing Choice]]

We will discuss 3 different representations of choices. 
- Preferences: Most primitive. Good axiomatic foundation
- Choice functions: Map most clearly to what's observed
- Utility functions: analytically very usefu. 

We'll demonstrate that these are essentially equivalent. 

## Choice Functions

Choice functions and preferences have to have 2 properties. Loosely:
1) "enough information"
2) "no contradictory information"

Together these are often called 'rational'. "Consistent" might be preferable, having less normative content. 

Let $X$ be some set of alternatives. $C()$ is a choice function such that $C(A)$ is a collection of alternatives chosen from $A \subseteq X$. If $P(X)$ is the power set of $X$, $C: P(X) \to P(X)$ s.t. $C(A) \subseteq A$. 

Two conditions. 

### Finite Nonemptiness
"Enough information":. Given non-empty $A$ and finite $A$, $C(A) \neq \emptyset$. 

Why must $A$ be finite? Consider $C(A) = \max A$; let $A = [0,1)$; oh no... 


### Coherence

Let $x,y$ be in $S \cap T$. $x \in C(S)$. $y \notin C(S)$. Then $y \notin C(T)$. We'll later discuss how this is the same as transitivity. 

The intuition here is: In $S$, I had the choice of $y$, I chose $x$ over $y$. Therefore, when looking at $T$: both $x$ and $y$ are choices. I may not choose $x$ - there might be something in $T \cap S^c$ that's better than $x$. But if I choose $y$ - why didn't I choose $x$? 


## Preferences

Preference is some subset of the set of pairs - a description of which is 'preferred'. We write $x \succsim y$; "$x$ is at least as good as $y$."  

From this, we can create $x \succ y$ - $x$ is strictly better than $y$, which is true when $x \succsim y$ but $\neg(y \succsim x)$. 

I can also make $x \sim y$, or $x$ is indifferent to $y$, which is the case when both $x \succsim y$ and $y \succsim x$. 

I once more have two cond
