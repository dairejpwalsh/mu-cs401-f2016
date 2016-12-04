## Reinforcement Learning
Reinforcement learning is closer to the goals of classic machine learning  
![Diagram](https://webdocs.cs.ualberta.ca/~sutton/book/ebook/figtmp7.png)
Reinforcement learning is when you train by allowing your system interact with a world by actions and feed it with state information and rewards  
Exploring the world can be a good subgoal even if you want to perform a specific task as the system can learn some properties of the world initially  
We can also provide a penalty for certain actions deemed extremely bad  
We want to learn a policy for interacting with the world (for example how to play tennis)  

States s_i: contains all relevant information about the environment  
Actions a_i: possible moves  
∏: states -> action  
Actions effect the world into the future  

Predictions (e.g. weather)
Will it rain on Saturday?
The earlier we can make the prediction correctly the better  

```
Day of Week   -          ______  
                    \   |      |  
clouds        -       > |  🖥  |-->P(rain on Saturday)  
temp          -     /   |______|  
satalite      -    
```

Error Function: did it rain on saturday?  
![Error](img/lecture-20/Error.png)  
How surprised are we that this happens?  
![xent](img/lecture-20/xent.png)  
![original model](img/lecture-20/original model.png)  

![TD model](img/lecture-20/TD model.png)

![TD error](img/lecture-20/TD error.png)


What if we observe a board game and bet on the outcome?  
![board game states](img/lecture-20/board game states.png)  
Says the above requires less data  

Algorithms called TD(λ) - Temporal Difference  

[TD Gammon](https://en.wikipedia.org/wiki/TD-Gammon)
* plays Backgammon
* s(t)  s(t+1)
* r(t)  r(t+1)
* a(t) a(t+1)  


![gammon reward](img/lecture-20/Gammon reward.png)
