---
date updated: 2021-07-28 16:48

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/stats/networks'
- '#status/📦'
---

## [[Networks 101]]

Source: <a href='zotero://select/items/0_5JAI9KIQ'>Scott. 2017-03-21. <i>Social Network Analysis</i></a>
Source:  <a href='zotero://select/items/0_2BSA49HJ'>Kadushin. 2011-12-05. <i>Understanding Social Networks: Theories, Concepts, and Findings</i></a>_


### Scott: Ch 6 Basic concepts

Adjacency: Connected by an edge
Isolate: Pt with no adjacent nodes
Neighborhood - all nodes adjacent to a point
Degree: How many nodes in neighborhood?
	- For directed graphs, separable into in-degree and out-degree
Density: How connected are the nodes
	- % of points isolate - "inclusivity"
	- Density: % of all possible connections that exist

Density formula:
$$\frac{l}{n(n-1)/2}$$
where $l$ is number of lines present, $n$ is number of nodes
	- what about weighted graphs? no consensus.
	- Density depends on size. not comparable across networks
	- No current consensus on methods for "absolute density"
	
### Scott: Centrality

Core ideas about _stars_ or influencers

Most straightforward concept is degree. If u have high degree - many connections. 
- But this is locally biased measure
- Can do paths of length 2. but for much more than 2, too many ppl are connected to too many others
- Not generalizable across networks. But we can have a measure of _relative_ centrality which is ur degree/$n$

What about an idea of global centrality? 
- _Sum Distance_: A point can be at short distances from many other points. an extension of degree concepts. Can simply sum the _geodesics_, shortest paths to all other points. Lowest sum is most central. 
- _Betweenness_ Another concept of centrality. To what extent is a point between other points in a graph? This becomes computationally more complex. 
	- _Betweenness Proportion_: A point Y can be between X and Z to an extent given by (0,1). This is the proportion of paths between X and Z that go through Y. 
	- _Pair Dependency_: X is pair-dependent on Y if many of the paths from X to all other points go through Y. If you are a shut-in with just 1 friend, you have 100% pair dependency on them. 
	- _Local Dependency Matrix_: Pair dependency is a property of two points in a network. We can write all of these pairs in a matrix. In cell $m_{i,j}$ is the pair-dependency between $i$ and $j$. 
	- _Betweenness Centrality_: The sum of pair dependency cores for a point, i.e. column sum of the dependency matrix - divided by 2 for double counting path from X to Y and Y to X. Intuitively - what proportion of paths btwn other pts in graph go through that point. 


Can also measure the degree of centralization in a graph as a whole. 
	- core concept is an idea of "centrality inequality" - my phrase. How much more central is the most central pt?  Centralization is the difference between that central pt and all other points, divided by the max possible sum of differences. 
	- Eg. a star-shaped graph would be maximally centralized.
	- This can be generalized to groups  -   how central is a group? Can be extended into notions of center, margin, periphery of a network, though not without subjective judgments. I omit detailed discussion

What is the absolute center of a graph?
	- the point that is closest to all other points. Create a distance matrix = shortest distance between each pair of points. The max of each column is a point's _eccentricity_. 
		- Can just say the least eccentric point is the center. If there are several points, then there is 


### Scott: Ch 7 Groups, Factions, Social Divisions

Inside a graph, there are subgraphs - any subset of points, with the nodes connecting those points. This is an important concept for studying cliques, factions etc. 

We can look for subgraphs that reflect naturally existing structures within a graph.
	- These should have structural determinants, like connectedness etc. 
	- They should be _maximal_ in relation to their particular quality - i.e. the biggest subgraph that can be formed without the quality disappearing.
	
	
##### Components
	
_Component_ subgraphs are a maximal connected subgraph. i.e. all points in the component can reach all other points, but no point in the component can reach outside it. 

In directed graphs, we can have _strong components_ and _weak components_. A strong component is one where all lines flow in a constant direction. But we could also pretend it's undirected and find the weak components

What's inside a component? Are there _blocks_ inside a component - subgraphs without a _cut point_ (a point that, if removed, would split the component into different components). Blocks are also called _knots_. Cut points can be interpreted as central pts or bridges between two blocks


##### Cycles

A _cycle_ is a path of any length that returns to its own starting point. Cycles can be described by length - $k$-cycles have length $k$. 

_Bridges_ are connections between two cycles that aren't part of either.

A _cyclic component_ is a chain of intersecting cycles.  Can find them by removing all bridges. 

Directed graph analogue is the _semicycle_ - but, of course, we can have _directed cycles_ A>B>C>A


##### Cliques

A _clique_  is  a set of points that are all connected to each other, and are not inside a clique. 


### Scott: Ch 8 Structural Locations, Classes, Positions


##### Clusters

Clusters are a set of points that are similar in some way. The nature of the cluster depends on where you set cutoffs on similarity - if you say "any degree whatsoever", you might have the whole graph.

You can cluster starting at the bottom and adding points, or starting with everyone and adding divisions. 


### Kadushin: Ch 4 Network Segmentation

Networks have internal structure: divisions of a company, states in the world etc. 
- There is _emic_ and _etic_ structure: emic structures are named or recognized by the people in the network (a nation-state, a high school clique); etic structures are defined by researchers (cycles, components etc)
- These exist in fuzzy states in reality, and are to some extent solidified by researchers for analysis purposes. 

Examples: 
 - Primary group is a group that's fundamental to the social formation of ppl. Their "most important" group?
 - Clusters are non overlapping
 
 Two key concepts:
 - Cohesiveness or closure
 - reaching out or "structural similarity"

Cohesiveness is embodied by cliques - a subgraph of at least three nodes that are all connected to each other. Any person can at most be in one clique (if they're in two, the cliques must be joined together). But we need something bigger than that. So various people have developed cluster finding definitions and methods. 
	- compare a subgraph to random subgraph - is it more connected? [Random within population params?] 
	- People can only be in 1 grp - strong assumption
	- Can also use a concept of group cohesion. How resistant is a group to disruption? If you removed random nodes, would the group break up? 
	
But we can also group nodes by how they relate to the whole graph: _structural similarity._ i.e. you could look at a directed org chart and identify managers vs employees, even tho managers are not connected to each other. 


