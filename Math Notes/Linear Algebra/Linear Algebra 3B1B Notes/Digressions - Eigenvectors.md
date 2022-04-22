---
date updated: 2021-06-16 21:25

notetype: "Math Class Note"
cssclass: math-class-note

tags: 
- '#classes/math/linalg'
---

#### [[Digressions - Eigenvectors]]
 
 ##### Finding Eigenvectors
 
 
 In [[Video 14 Eigenvalues and Eigenvectors|Video 14]], we found eigenvalues $\lambda = 1$ and $\lambda = 4$ for the matrix $A = \begin{bmatrix} 2 & 2 \\ 1& 3 \end{bmatrix}$. 
 
Plug in $4$.  Now we need to find $v_1, v_2$ such that 
 
 $$\begin{bmatrix} -2 & 2 \\ 1 & -1\end{bmatrix}\begin{bmatrix}v_1\\v_2\end{bmatrix}= 0$$
 
Gaussian elimination can get us 
  $$\begin{bmatrix} -1 & 1 \\ 0 & 0\end{bmatrix}\begin{bmatrix}v_1\\v_2\end{bmatrix}= 0$$
  
  So we have $v_1 = v_2$ - all of the vectors on the line $y=x$ are eigenvectors (such as $(1,1$).)
  
  Now let's find $\lambda = 1$. 
  
  $$ \begin{bmatrix} 1 & 2 \\ 1 & 2\end{bmatrix}\begin{bmatrix}v_1\\v_2\end{bmatrix}= 0$$
  
   $$ v_1 = -2v_2$$
   
So, the vectors on the line $-2y = x$ are also eigenvectors (such as $(-2, 1)$).
   
   
##### Change of Basis Adventures
   
Let $A$ be $\begin{bmatrix} 0 & 1 \\ 1 & 1 \end{bmatrix}$. Using eigenvectors and a change of basis, find a general form for $A^n$.

----------------

Let's do it the long way, to figure out what's happening. 
   
The first few powers by hand:
   
   $$\begin{array}{lcccl}
   A^2 &=& \begin{bmatrix} 0 & 1 \\ 1 & 1 \end{bmatrix}\begin{bmatrix} 0 & 1 \\ 1 & 1 \end{bmatrix} &=& \begin{bmatrix} 1 & 1 \\ 1 & 2 \end{bmatrix}\\
   A^3 &=& \begin{bmatrix} 0 & 1 \\ 1 & 1 \end{bmatrix}\begin{bmatrix} 1 & 1 \\ 1 & 2 \end{bmatrix} &=& \begin{bmatrix} 1 & 2 \\ 2 & 3 \end{bmatrix}\\
   A^4 &=& \begin{bmatrix} 0 & 1 \\ 1 & 1 \end{bmatrix}\begin{bmatrix} 1 & 2 \\ 2 & 3 \end{bmatrix} &=& \begin{bmatrix} 2 & 3 \\ 3 & 5 \end{bmatrix}
   \end{array}$$
   
This looks a lot like some sort of Fibonacci thing... Let's do some induction.
   
   
      
   $$ \begin{array}{lcccl}
   A^{k+1} &=& \begin{bmatrix} 0 & 1 \\ 1 & 1 \end{bmatrix}\begin{bmatrix} A^k_{1,1} & A^k_{1,2} \\ A^k_{2,1} & A^k_{2,2} \end{bmatrix} &=& \begin{bmatrix} A^k_{2,1} & A^k_{2,2} \\ A^k_{1,1}+A^k_{2,1} & A^k_{1,2} + A^k_{2,2}\end{bmatrix}\\
   \end{array}$$
   
   
Suppose $A^k_{1,2} = A^k_{2,1}$. Then this simplifies to 

   
$$ \begin{array}{lcl}
A^{k+1} &=& \begin{bmatrix} A^k_{1,2} & A^k_{2,2} \\ A^k_{1,1}+A^k_{1,2} & A^k_{1,2} + A^k_{2,2}\end{bmatrix}\\
\end{array}$$
   
One more step. 

$$ \begin{array}{lcl}
A^{k+2} &=& \begin{bmatrix} A^{k+1}_{1,2} & A^{k+1}_{2,2} \\ A^{k+1}_{1,1}+A^{k+1}_{1,2} & A^{k+1}_{1,2} + A^{k+1}_{2,2}\end{bmatrix}\\
\end{array}$$
        
$$ \begin{array}{lcl}
   A^{k+2} &=& \begin{bmatrix} A^{k}_{2,2} & A^k_{1,2} + A^k_{2,2}\\ A^k_{1,2}+A^k_{2,2} & A^k_{1,2} + 2A^k_{2,2}\end{bmatrix}\\
   \end{array}$$
   
Let's see what this looks like starting with $k=2$:
   
$$ \begin{array}{lcl}
   A^{4} &=& \begin{bmatrix} 1+1 & 1 + 2\\ 1+2 & 2 + (1 + 2)\end{bmatrix}\\
   \end{array}$$
   
Here's our Fibonacci recurrence! 
   
   _______________
Now, in change of basis terms. 
   
What are the eigenvalues of $A$?
   
$$A = \begin{bmatrix} 0 & 1 \\ 1 & 1 \end{bmatrix} $$
 
Our characteristic polynomial is $\lambda^2 - \lambda -1$. Not easily factorable - so back to the quadratic formula. 
 
 $$ \lambda = \frac{-b \pm \sqrt{(b^2 - 4ac)}}{2a}  $$
$$ \lambda = \frac{1 + \sqrt{5}}{2}  $$
$$ \lambda = \frac{1 - \sqrt{5}}{2}  $$

Terrible. 
_______________
So then what are the eigenvectors?

$$(A- \lambda I)\mathbf{v} = \begin{bmatrix}   -\frac{1}{2} (1 \pm \sqrt{5}) & 1 \\ 1 & 1- \frac{1}{2}(1 \pm \sqrt{5})\end{bmatrix} \begin{bmatrix} v_1 \\ v_2 \end{bmatrix} = 0$$
$$\begin{bmatrix}   -\frac{1}{2}(1 + \sqrt{5})  & 1\\ 1 & 1 - \frac{1}{2}(1 + \sqrt{5})\end{bmatrix} \begin{bmatrix} v_1 \\ v_2 \end{bmatrix} = 0$$

$$\begin{bmatrix}   -\frac{1}{2}(1 + \sqrt{5})  & 1 &|& 0\\ 1 & 1 - \frac{1}{2}(1 + \sqrt{5})  &|& 0\end{bmatrix} $$
$$\begin{bmatrix}   -\frac{1}{2}(1 + \sqrt{5})  & 1 &|& 0\\ 1 & 
\frac{1}{2}(1 - \sqrt{5})  &|& 0\end{bmatrix} $$
$$\begin{bmatrix}   -\frac{1}{2}(1 + \sqrt{5})(\frac{1}{2}(1 - \sqrt{5}))  & \frac{1}{2}(1 - \sqrt{5}) &|& 0\\ 1 & 
\frac{1}{2}(1 - \sqrt{5})  &|& 0\end{bmatrix} $$

$$\begin{bmatrix}   -\frac{3}{2}  & \frac{1}{2}(1 - \sqrt{5}) &|& 0\\ 1 & 
\frac{1}{2}(1 - \sqrt{5})  &|& 0\end{bmatrix} $$

$$\begin{bmatrix}   1  & 0 &|& 0\\ 0 & 
\frac{1}{2}(1 - \sqrt{5})  &|& 0\end{bmatrix} $$

First eigenvector, $(2, 1 - \sqrt{5})$. The other one works out to be $(2, 1 + \sqrt{5})$.

_______________

So we know the change of the basis matrix: 

$$B = \begin{bmatrix} 2 & 2 \\  1 + \sqrt{5}  & 1 - \sqrt{5}\end{bmatrix}$$

$$B^{-1} \rightarrow \begin{bmatrix} 2 & 2 &|&0 & 0 \\  1 + \sqrt{5}  & 1 - \sqrt{5} &|&0 & 0\end{bmatrix}$$

$$\begin{bmatrix} 2(1 + \sqrt{5}) & 2(1 + \sqrt{5}) &|&1 + \sqrt{5} & 0 \\  2(1 + \sqrt{5})  & 2(1 - \sqrt{5}) &|&0 & 2\end{bmatrix}$$

$$\begin{bmatrix} 2(1 + \sqrt{5}) & 2(1 + \sqrt{5}) &|&1 + \sqrt{5} & 0 \\  0 & -4 \sqrt{5} &|&-1(1+ \sqrt{5}) & 2\end{bmatrix}$$

$$\begin{bmatrix} 2(1 + \sqrt{5}) & 2(1 + \sqrt{5}) &|&1 + \sqrt{5} & 0 \\  0 & 20 &|&\sqrt{5}(1+ \sqrt{5}) & -2\sqrt{5}\end{bmatrix}$$

$$\begin{bmatrix} 1 & 1 &|&\frac{1}{2} & 0 \\  0 & 1 &|&\frac{1}{20}(\sqrt{5}+ 5) & -\frac{1}{20}2\sqrt{5}\end{bmatrix}$$


$$\begin{bmatrix} 1 & 0 &|&\frac{10}{20} - \frac{(\sqrt{5}+ 5)}{20} & \frac{1}{20}2\sqrt{5} \\  0 & 1 &|&\frac{1}{20}(\sqrt{5}+ 5) & -\frac{1}{20}2\sqrt{5}\end{bmatrix}$$


$$B^{-1} = \frac{1}{20}\begin{bmatrix}&5 - \sqrt{5} & 2\sqrt{5} \\  &\sqrt{5}+ 5 & -2\sqrt{5}\end{bmatrix}$$

Now to find $A_b$:

$$\begin{array}{ccl}
B^{-1}AB &=&  \frac{1}{20}\begin{bmatrix}&5 - \sqrt{5} & 2\sqrt{5} \\  &\sqrt{5}+ 5 & -2\sqrt{5}\end{bmatrix}\begin{bmatrix} 0 & 1 \\ 1 & 1 \end{bmatrix} \begin{bmatrix} 2 & 2 \\  1 + \sqrt{5}  & 1 - \sqrt{5}\end{bmatrix} \\

&=& \frac{1}{20}\begin{bmatrix}&5 - \sqrt{5} & 2\sqrt{5} \\  &\sqrt{5}+ 5 & -2\sqrt{5}\end{bmatrix} \begin{bmatrix} 1 + \sqrt{5} & 1 - \sqrt{5}\\ 3 + \sqrt{5} & 3 - \sqrt{5} \end{bmatrix} \\

&=& \frac{1}{20}  \bigg[  \begin{array}{} (5 - \sqrt{5} )(1 + \sqrt{5})+ (2 \sqrt{5})(3 + \sqrt{5}) \\ (5 + \sqrt{5})(1 + \sqrt{5})+(-2 \sqrt{5})(3 + \sqrt{5})\end{array} \\
&&\begin{array}{} (5 - \sqrt{5})( 1 - \sqrt{5})+(2 \sqrt{5})(3 - \sqrt{5})\\ (5 + \sqrt{5})( 1 - \sqrt{5})+(-2 \sqrt{5})(3 - \sqrt{5}) \end{array}  \bigg]\\

&=& \frac{1}{20}  \bigg[  \begin{array}{} (5 -\sqrt{5} + 5\sqrt{5} - 5)+ (6 \sqrt{5} + 10) \\ (5 + \sqrt{5} + 5\sqrt{5} + 5)-(6 \sqrt{5} + 10)\end{array} \\
&&\begin{array}{} (5 - \sqrt{5}-5\sqrt{5} + 5)+(6 \sqrt{5} - 10)\\ (5 - 5\sqrt{5} + \sqrt{5} - 5)-(6 \sqrt{5} - 10) \end{array}  \bigg]\\ 


&=& \frac{1}{20} \begin{bmatrix} 10 + 10\sqrt{5}  & 0 \\ 0 & 10 -10 \sqrt{5}) \end{bmatrix}\\

&=& \frac{1}{2} \begin{bmatrix} 1 + 1\sqrt{5}  & 0 \\ 0 & 1 -1 \sqrt{5} \end{bmatrix}
\end{array}
$$

Returning to the original problem, 

$$ A_b^n =  \begin{bmatrix} (\frac{1 + \sqrt{5}}{2})^n  & 0 \\ 0 & (\frac{1 - \sqrt{5}}{2})^n \end{bmatrix} = $$

Let's substitute in the golden ratios $\phi = \frac{1 + \sqrt{5}}{2}$ and $\psi = -\frac{1}{\phi} =\frac{1 - \sqrt{5}}{2}$.

$$ A_b^n =  \begin{bmatrix} \phi^n  & 0 \\ 0 & \psi^n \end{bmatrix} $$



Wolfram alpha test for $n =5$: 

$$\begin{bmatrix} 2 & 3 \\ 3 & 5 \end{bmatrix}$$


Now let's go back:

$$\begin{array}{ccl}

BA_b^nB^{-1} &=& \frac{1}{20}\begin{bmatrix} 2 & 2 \\  1 + \sqrt{5}  & 1 - \sqrt{5} \end{bmatrix} \begin{bmatrix} \phi^n  & 0 \\ 0 & \psi^n \end{bmatrix}\begin{bmatrix}&5 - \sqrt{5} & 2\sqrt{5} \\  &\sqrt{5}+ 5 & -2\sqrt{5}\end{bmatrix}\\

 &=& \frac{1}{10}\begin{bmatrix} 1 & 1 \\  \phi  & \psi \end{bmatrix}
 \begin{bmatrix} \phi^n  & 0 \\ 0 & \psi^n \end{bmatrix}
 \begin{bmatrix}&5 - \sqrt{5} & 2\sqrt{5} \\  &\sqrt{5}+ 5 & -2\sqrt{5}\end{bmatrix}\\
 
 &=& \frac{1}{10} \begin{bmatrix} \phi^n  & \psi^n \\ \phi^{n+1} & \psi^{n+1}  \end{bmatrix}
 \begin{bmatrix}&5 - \sqrt{5} & 2\sqrt{5} \\  &\sqrt{5}+ 5 & -2\sqrt{5}\end{bmatrix}\\

&=& \frac{1}{10} \bigg[ \begin{array}{}(\phi^n)(5 - \sqrt{5} ) +(\psi^n )(\sqrt{5}+ 5) \\  (\phi^{n+1})(5 - \sqrt{5} ) +(\psi^{n+1})(\sqrt{5}+ 5) \end{array}\\
  
 &&\begin{array}{}(\phi^n )( 2\sqrt{5}) +(\psi^n )(-2\sqrt{5}) \\  (\phi^{n+1})(2\sqrt{5}) +(\psi^{n+1})(-2\sqrt{5})\end{array}\bigg] \\

&=&\bigg[ \begin{array}{}(\phi^n)(\frac{1}{2} - \frac{1}{2\sqrt{5}}  ) +(\psi^n )(\frac{1}{2\sqrt{5}} + \frac{1}{2}) \\  (\phi^{n+1})(\frac{1}{2} - \frac{1}{2\sqrt{5}} ) +(\psi^{n+1})(\frac{1}{2\sqrt{5}} + \frac{1}{2}) \end{array}\\
  
 &&\begin{array}{}(\phi^n )(\frac{1}{\sqrt{5}}) -(\psi^n )(\frac{1}{\sqrt{5}}) \\  (\phi^{n+1})(\frac{1}{\sqrt{5}}) -(\psi^{n+1})(\frac{1}{\sqrt{5}})\end{array}\bigg] \\
 
 &=&\bigg[ \begin{array}{}\phi^n(\frac{\sqrt{5} - 1}{2\sqrt{5}}  ) +\psi^n(\frac{1 + \sqrt{5}}{2\sqrt{5}}) \\  \phi^{n+1}(\frac{\sqrt{5} - 1}{2\sqrt{5}} ) +\psi^{n+1})(\frac{1+ \sqrt{5}}{2\sqrt{5}}) \end{array}\\
  
 &&\begin{array}{}\frac{\phi^n-\psi^n}{\sqrt{5}} \\  \frac{\phi^{n+1}-\psi^{n+1}}{\sqrt{5}}\end{array}\bigg] \\
 
  &=&\bigg[ \begin{array}{}-\frac{1}{\sqrt{5}}\phi^n(\frac{1-\sqrt{5}}{2}  ) +\frac{1}{\sqrt{5}}\psi^n(\frac{1 + \sqrt{5}}{2}) \\
  -\frac{1}{\sqrt{5}}\phi^{n+1}(\frac{1-\sqrt{5}}{2} ) +\frac{1}{\sqrt{5}}\psi^{n+1}(\frac{1+ \sqrt{5}}{2}) \end{array}\\
  
 &&\begin{array}{}\frac{\phi^n-\psi^n}{\sqrt{5}} \\  \frac{\phi^{n+1}-\psi^{n+1}}{\sqrt{5}}\end{array}\bigg] \\
 
  &=&\begin{bmatrix}
  -\frac{\phi^n\psi +\psi^n\phi}{\sqrt{5}} &
  \frac{\phi^n-\psi^n}{\sqrt{5}}  \\
  -\frac{\phi^{n+1}\psi +\psi^{n+1}\phi}{\sqrt{5}} & 
   \frac{\phi^{n+1}-\psi^{n+1}}{\sqrt{5}}
   \end{bmatrix}\\
  
&=&\begin{bmatrix}
  \frac{\phi^{n-1} - \psi^{n-1}}{\sqrt{5}} &
  \frac{\phi^n-\psi^n}{\sqrt{5}}  \\
   \frac{\phi^n-\psi^n}{\sqrt{5}} & 
   \frac{\phi^{n+1}-\psi^{n+1}}{\sqrt{5}}
   \end{bmatrix}\\
\end{array} 
$$

