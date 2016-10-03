# Gambling Problem

Let's say you walk into a pub  
There's n people in this pub and a game is playing on the T.V.  
Everyone there is an expert and you must place a bet on which team will win. No bet no service  
Obviously we want to keep our money/not lose

Strategies  
* we can rely on the experts
* we must place a new bet on a new game each day
* we can further assume that one of the experts is always right  


The prediciton os expert i on day t is denoted as follows  
![expert i's prediction on day t](/img/lecture-05/XiT in -+.png)  

On the first day we give all experts a base weight of 1 as we don't know how reliable they are

![original weight for all experts](/img/lecture-05/original weight.png)  

Then we make our prediction for the first day.  
![prediction on day 1](/img/lecture-05/prediction on day 1.png)  
As some experts say -1 and others say +1 we choose the team most people voted for.  
![weight after day 1](img/lecture-05/weight after day 1.png)  
Then we update the weight we give each expert to reflect their performance on the first day. If they were correct then their weight stays the same, otherwise we set the contents of the brackets to 0 or -1  

We then use these weights in our predictionds for day 2, this means we disregard the opinions of the people who were incorrect on the first day which helps us narrow down the list of possibly always correct experts  
![prediction on day 2](/img/lecture-05/prediction on day 2.png)  

More generally we get the equations  
![general weights formula](img/lecture-05/general weights formula.png)  

![general prediction formula](/img/lecture-05/general prediction formula.png)


We can thus model our loss as  
![loss function](/img/lecture-05/loss function.png)  
As t increases the number of losses should decrease as we'll eventually know our always correct expert  
![loss limit](/img/lecture-05/loss limit.png)  



## What if the best expert is not perfect
Then we can change our weight function to instead prefer people who are mostly correct  
![not perfect weight change](img/lecture-05/notPerfect weight change.png)  
Max of n errors  
![optimal w](img/lecture-05/optimal w.png)  

![weight sum](img/lecture-05/weight sum.png)


for each loss ![w decrease per loss](img/lecture-05/w loss.png)  

Initially our weights are:  
w(1) = n  
Subesequently after a few iterations we have the following bounds on our weights  
![wt upper bound](img/lecture-05/wt upper bound.png)

![wt lower bound](img/lecture-05/wt lower bound.png)

Thus w(t) is bound above and below as  
![boundaries](img/lecture-05/boundaries.png)  

![log boundaries](img/lecture-05/log boundaries.png)  

![lower bound](img/lecture-05/lower bound.png)


## Gradient Descent
Gradient descent uses and additive update to the weights  
![gradient descent](img/lecture-05/gradient descent.png)  
With Error function defined as  
![gradient descent error function](img/lecture-05/gradient descent error function.png)  

![weight updates gradient descent](img/lecture-05/weight updates gradient descent.png)  
As a compound function  
![compound weight update](img/lecture-05/compound weight update.png)  
For this to converge we must have that  

![convergence criterion](img/lecture-05/convergence criterion.png)  
Which is equivalent to  
![convergence criterion expanded](img/lecture-05/convergence criterion expanded.png)  
Where zeta is the learning rate (how fast we move in the direction we thing will minimize our error function)  

![learning rate bounds](img/lecture-05/learning rate bounds.png)
