---
aliases:
creation date: 2023-02-19 13:05
date updated: 2023-02-19 13:05

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[🚧Game Theory 501 I - Setup]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## Definitions

An <font color=gree>extensive form</font> is a graph representation of a game. Relevant definitions: 
- A directed graph: $G = \{ V, E\}$ with an edge being an ordered pair 
- A path is a sequence of nodes $x_1, x_2, \ldots$ in $V$ such that $x_1,x_2 \in E$, $x_2, x_3 \in E$ and so on. 

A <font color=gree>tree</font> is a digraph $T$ such that 
- There is a node $r$, a root, such that $\nexists x \in X(T)$ such that $(x, r) \in E$, and  
- $x \in X(T)$ implies a unique path from $r$ to $x$. 

The <font color=gree>length</font> of a path is the number of edges in it. The <font color=gree>depth</font> of a tree is the length of the longest path in it.

<font color=gree>Children</font> of node $x$ are all nodes $y \in X(T)$ such that $(x,y) \in E$. <font color=gree>Descendants</font> are all the children's children and so on. Same idea

A <font color=gree>subtree:</font> given $x \in X(T)$, $T_x$ is a subtree starting with $x$ when $x$ can be a root for all its descendants in $T$. 

