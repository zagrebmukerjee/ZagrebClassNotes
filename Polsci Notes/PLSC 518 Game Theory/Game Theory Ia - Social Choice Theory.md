---
aliases:
- 'Arrow Impossibility Theorem'
creation date: Thursday, September 15th 2022, 5:50 pm
date updated: Thursday, September 15th 2022, 5:54 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#status/🚧'
---

# [[Game Theory Ia - Social Choice Theory]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

### Basics 
Game theory arose to some degree as a spinoff of social choice theory. 

Social choice theory involves the aggregation of preferences. One method was to produce decision rules, but this was not very systematic. So there was an attempt to create a set of axioms, desirable properties of a decision rule, and see what could satisfy them. 

Establish a primitive notion of [[Micro Theory I - Representing Choice#Preferences|preferences]]. Assume them to be complete and transitive. 

Define an <font color=gree>aggregation rule</font> as a function that takes in preferences and returns a social choice. 

Examples: 
- Dictatorial. Pick person $i$'s preferences
- Simple majority. $x \succsim_S y$ if and only if at least $n+1/2$ people have $x \succsim_i y$. 
- Supermajority
- Borda count: each voter ranks, and then assign preferences based on rank order. 

Suppose we require that a rule satisifies: 
- transitivity 
- non-dictatorial: there exists agent $i$ such that if $a \succsim_i b$ and $b \succ_j a \; \forall \, j: j\neq i$ then the social choice cannot be $x \succ y$. This is a very weak concept of non-dictatorial!
- Weakly Paretian: if $\forall i$, $x \succ_i y$, then $x \succsim_S y$. 
- Independence of irrelevant alternatives: Consider two preference profiles $p$ and $p'$ where every individual has the same ranking for $x$ and $y$. Then the rule satisfies IIA if it ranks $x,y$ the same under $p$ and $p'$. 
	- When IIA is violated, this tends to map to incentives for misreporting preferences. 

### Theorems

**Arrow's Theorem**: Given more than 3 people, more than 3 alternatives: can't have preferences that are all of (transitive, non-dictatorial, weakly paretian, IIA). 

This is a claim about aggregation rules over unrestricted domains: I require that an aggregation rule can handle any type of preference profile. In some sense this is excessive generality. We can restrict the domain - throw out some parts until we can satisfy our axioms again. For instance, we can have only 2 options, or single-peaked preferences. 

'Single-peaked' preferences: every agent has some preferred option $x_i$. Based on some distance metric, their utility $u_i(y)$ falls off with $|x_i - y|$. 

Then we can get:

**Median Voter Theorem**: Given signel peaked preferences, the decision rule $x = \text{median} \{x_i^*\}$ will under majority rule have $x \succsim y$ for all other $y$.  