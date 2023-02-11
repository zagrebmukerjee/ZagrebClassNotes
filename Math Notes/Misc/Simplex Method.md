---
aliases:
creation date: Saturday, February 11th 2023, 2:26 pm
date updated: Saturday, February 11th 2023, 5:07 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes'
- '#status/🚧'
---

# [[Simplex Method]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>


[[Optimization]]
[[Linear Programming]]



Objective: Solve a linear programming problem: that is, maximization of a linear objective function subject to a set of linear-inequality constraints. 

Fundamentally, these inequalities represent a polytope and the maximum lies at one of the corners. The simplex method will pick the maximal corner quickly. 

## Example Problem

### Setup

Someone wants to maximize their earnings. They have 12 hours per week to work, and 16 hours per week to prepare. There are two jobs: 
- Job 1 pays $40/hr and requires 2 hours of preparation per hour worked, and 
- Job 2 pays $30/hr and requires 1 hour of prep/hour of work. 

Then this is a linear programming problem. Let $x_1, x_2$ be hours in Jobs 1 and 2. Then: 

Maximize 
$$40x_1 + 30x_2$$
subject to: 
$$ x_1 + x_2 \leq 12$$ 
$$2x_1 + x_2 \leq 16$$
and 
$$ x_1 \geq 0 ; \; x_2 \geq 0$$






### Step 1: Slack

Rewrite the maximization problem as $w - 40x_1 -30x_2 = 0$, where $w = \max 40x_1 + 30x_2$. Let $y_1$ represent leftover hours worked, and $y_2$ lefover preparation hours. Then the inequality constraints become equalities, leaving us with 
$$\begin{align}
x_1 + x_2 + y_1 &= 12\\
2x_1 + x_2 + y_2 &= 16\\
w - 40x_1 -30x_2 &= 0\\
\end{align}$$
Now we can make an augmented matrix, the <font color=gree>Simplex Tableau</font>:
$$
\begin{array} {ccccc|c}
x_1 & x_2 & y_1 & y_2 & w & C\\\hline
1 & 1 & 1 & 0 & 0 & 12\\
2 & 1 & 0 & 1 & 0 & 16\\\hline
-40 & -30 &0 &0 &1 & 0
\end{array}
$$


By construction, the last four columns are the solutions to some system of equations, a reduced row-echelon form: $y_1 = 12, y_2 = 16, w = 0$, implying $x_1 = x_2 = 0$. 
$$
\begin{array}{ccc|c}
y_1 & y_2 & w & C\\
\hline
1 & 0 & 0 & 12\\
0 & 1 & 0 & 16\\
0 & 0 & 1 & 0\\
\end{array}
$$

This is the <font color=gree>basic solution</font> from this simplex tableau; it corresponds to a corner of the polytope (the worst corner),


### Step 2: Pivot

As a sort of 'fastest route around the corners', choose the highest-coefficient variable in the objective function: in this case, $x_1$.


$$
\begin{array} {ccccc|c}
x_1 & x_2 & y_1 & y_2 & w & C\\\hline
1 & 1 & 1 & 0 & 0 & 12\\
2 & 1 & 0 & 1 & 0 & 16\\\hline
\cellcolor{#8b0000}-40 & -30 &0 &0 &1 & 0
\end{array}
$$

Divide the rightmost column constants by the coefficients on the candidate variable, and choose the lowest-valued row. 
$$
\begin{array} {ccccc|c}
x_1 & x_2 & y_1 & y_2 & w & C\\\hline
1 & 1 & 1 & 0 & 0 & 12/1 = 12\\
\cellcolor{#020202}2 &\cellcolor{#020202} 1 &\cellcolor{#020202} 0 &\cellcolor{#020202} 1 &\cellcolor{#020202} 0 & \cellcolor{#020202}16/2 = 8\\\hline
\cellcolor{#8b0000}-40 & -30 &0 &0 &1 & 0
\end{array}

$$

Then use row operations to 'solve' for the chosen variable (ie. zero out its column). Subtract 1 from 2

$$
\begin{array} {ccccc|c}
x_1 & x_2 & y_1 & y_2 & w & C\\\hline
1 & 1 & 1 & 0 & 0 & 12\\
1 & 0 & -1 & 1 & 0 & 4\\\hline
-40 & -30 &0 &0 &1 & 0
\end{array}
$$
Subtract 2 from 1: 

$$
\begin{array} {ccccc|c}
x_1 & x_2 & y_1 & y_2 & w & C\\\hline
0 & 1 & 2 & -1 & 0 & 8\\
1 & 0 & -1 & 1 & 0 & 4\\\hline
-40 & -30 &0 &0 &1 & 0
\end{array}
$$
