---
aliases:
creation date: Saturday, February 25th 2023, 5:54 pm
date updated: Saturday, February 25th 2023, 6:01 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Game Theory 501 Ia - Backward Induction]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>

## Game of Nim

Play Nim as follows: 

There are three piles of matchsticks, with $n_i$ sticks in pile $i$. Each player in turn chooses a pile, and takes one or more. THe winner is the person who takes the last stick. 

For intuition: Suppose we have 2 piles of matchsticks with the same number of sticks. Then Player $2$ has to win: if Player $1$ takes $x$ matchsticks from pile $i$, Player $2$ can take $x$ from pile $j$. 

With 2 piles and a different number, Player $1$ can take enough from one pile to equalize them, and then they're in the equalized scenario but with the order reversed. 

For more advanced analysis the game can be represented as a matrix, with each row being the binary representation of the number of sticks in each pile. Example: the triple $(11,12,7)$ becomes the matrix 


$$
\begin{bmatrix} 
1 & 0 & 1 & 1\\
1 & 1 & 0 & 0 \\
0 & 1 & 1 & 1\\
\end{bmatrix}$$

The game can be approached as follows: A position is *safe* if the sum of every column is even. Otherwise it is unsafe. 
The win state of $0$ is a safe position. So I want to be handed a position and then turn it safe. 

Not a tremendously interesting game - though the object of a reasonable amount of analysis - but serves as a good introduction to the intuition around backward induction. 


## Backward Induction 

![[Game Theory 501 Ia - Backward Induction 2023-02-25 18.11.14.excalidraw|300]]

This game has a subgame for each non-terminal node 