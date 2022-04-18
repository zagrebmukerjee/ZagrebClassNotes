![[Pasted image 20220418193143.png]]


1. Precisely interpret the coefficient on 'black'

The coefficient means that, all else equal, I would expect a black person in the scope of this study to make $2173 less than a white person.

2. Precisely interpret the coefficient on 'log re74'
The coefficient means that, all else equal, a $10\%$ increase in 1974 income is associated with a roughly $850 increase in income.
3. What is the $t$ statistic for the null hypothesis that $\beta_2$ is $0$
$(\beta_2 - 0)/\text{SE}_2 = 60/44 = 1.33$

4. True or false - the $F$ statistic in the table means that we reject the null hypothesis that all the coefficients in the model are equal to $0$
True. The f statistic is for the omnibus test of all coefficients
<font color=red>actually FALSE. it's against an intercept only model. </font>

5. True or false? Suppose the  true model of real earnings  in 1978 doesn’t depend on  
race. Including the variable  therefore induces bias in our  estimates of the regression  coefficients.
False. Adding an orthogonal variable won't bias the coefficients. 


6. Looking at Model 2, express the marginal effect of treatment in terms of the coefficients and variables. 
Marginal effect of treatment is $699 + $1261 if you are black


7. What is the variance of the marginal effect?
The variance is $\text{SE}_1^2 + \text{SE}_2^2 + 2 \cov (\betahat_1, \betahat_2)$. where $\text{SE}_1$ is 1558, $\text{SE}_2$ is 1702, the covariance comes from the variance-covariance matrix. 

8. A classmate proposes you test the null hypothesis $\beta_2 = \beta_4$. Write the appropriate test statistic based on the information in Model 2. 

We can use the $t$ test for a difference in coefficients, since saying $\beta_2 = \beta_4$ is the same as saying $\beta_2 - \beta_4$ is $0$. So our test statistic is 

$$t = \frac{\betahat_2 - \betahat_4}{\sqrt{44^2 + 82^2 - 2 \cov(\betahat_2, \betahat_4)}}$$