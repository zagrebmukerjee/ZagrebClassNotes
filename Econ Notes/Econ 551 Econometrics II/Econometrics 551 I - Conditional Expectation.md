---
aliases:
creation date: Friday, January 27th 2023, 1:06 pm
date updated: Friday, January 27th 2023, 1:07 pm

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#types/classes/econ'
- '#status/🚧'
---

# [[Econometrics 551 I - Conditional Expectation]]
<span style = "font-size:120%"><i >Zagreb Mukerjee </i></span>



Defining conditional expectations in terms of conditional probabilities becomes a bit messy when thinking about continuous RVs, and we risk dividing various things by zero. Instead, we can define it implicitly as a projection. Because when has defining something implicitly not been clarifying?

### Definition

First introduce the notion of a <font color=gree>square-integrable</font> function; this means that the square of the absolute value is integrable. This lets us say that if $E[X^2] < \infty$ then $E[f(X)^2] < \infty$. Let $M$ be the space of square-integrable functions. 
