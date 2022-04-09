---
date updated: 2021-06-18 12:58

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classnotes/math/calculus'
---

### [[Video 2 Paradox of the Derivative]]

#### Overview

The derivative is frequently defined as an instantaneous rate of change - but this is somewhat of a paradox. Change happens over time - there can't be an instantaneous change. 

Suppose a car goes from A to B, 100 meters in 10 seconds. We can describe its cumulative distance traveled as a function of time $s(t)$, and its velocity as $v(t)$. 

![[Pasted image 20210618130258.png]]

In the image, you can see the car starting, accelerating to its max speed at ~ $t = 5$, and then slowing down. 

Exactly how does velocity depend on distance? Velocity can be defined based on a comparison between times and distances: $\frac{\Delta s}{\Delta t}$. 

But suppose we want a point estimate of velocity, such as a speedometer gives?

We can look at a small difference in time and distance. Let's have $ds$ be the small difference in distance and $dt$ the small difference in time. 

![[Pasted image 20210618130741.png]]

This is a function of time - the triangle here will change as the car speeds up and slows down. So we can say

$$ \frac{ds}{dt}(t) = \frac{s(t+dt) - s(t)}{dt}$$

As $dt \to 0$, this becomes an approximation of the rate of change at any particular point - the rate of change is represented also as the rise over run of the line tangent to the curve at any point. 

#### Example

Let $s(t) = t^3$. What is $\frac{ds}{dt}$?

As above, we have

$$\frac{s(t+dt) - s(t)}{dt}$$
$$\frac{(t+dt)^3 - t^3}{dt}$$

$$\frac{(t^3 + 3t^2dt + 3 tdt^2 + dt^3) - t^3}{dt}$$

$$\frac{3t^2dt + 3 tdt^2 + dt^3}{dt}$$

$$ 3t^2 + 3dt + dt^2$$

As $dt \to 0$, this approaches $3t^2$ since the $dt$ terms drop away. 

For the general case, and finding other properties of derivatives from this fraction, see: [[Digression - properties of derivative algebraically]]