## Reinforcement Learning

https://en.wikipedia.org/wiki/Reinforcement_learning

Reinforcement learning has become big. It used to not work well, and needs a few tricks to get it working.

![Diagram](https://webdocs.cs.ualberta.ca/~sutton/book/ebook/figtmp7.png)

S: state of the world
A: actions

An action is applied to a state, which gives a reward
r: S x A -> R

The new world state is update by the action
W: S x A -> S

The agent uses a policy (its "brain")
π: S -> R


Agent wants to maximise reward
The reward is amortised
0 < α < 1

R(t) = r(t) + α.r(t+1) + α².r(t+2) + ...

https://en.wikipedia.org/wiki/Bellman_equation


We could try the action that gives us the best immediate reward (greedy algorithm)

The issue with this approach is that we lose the long term rewards with this strategy.

π`(s) = action that gives the best amortised reward
 = argmax(a)(r(s, a) + αV(w(s, a)))
 
where V(s) is the estimate of R starting in state s and following optimal policy.
We will use π* to denote optimal policy.
 
πⱽ(s) = optimal policy given the value function.
 
### Policy-Value iteration

Meta-circular iteration.
Function that with repeated iterations hopefully will converge on a pair, the optimal policy and value.

Vπ(s) = value reached when following policy π
Vπ(s) = r(s, π(s)) + α.Vπ(w(s, π(s)))

If rewards are non-negative and we start at 0, we can only go up.
The proof involves showing that the maximum difference between any two elements decreases on each step.

#### Properties

It is a batch algorithm
We need a world model (there are tricks for stochastic worlds)

#### Examples

A video game monster AI, optimising its policy.

Solving a maze where the reward is leaving the maze.



### Q-Learning

Q(s, a) -> Amortised reward doing an action and then following optimal policy.
This is like doing something a bit different, then trying your best from that position.

Similar to policy-value expect the valuer function is called Q.
A nice property this has is that Q somehow knows optimal policy.

π*(s) = argmax(a)(Q(s, a))  # pick the best action


Q(s, a) = r(s, a) + α(max(a)(Q(w(s, a)), â))

This states that you can update one element of the table, improving the Q table even if the action is not optimal. Performing random actions still helps.
It also means it is an online algorithm.


A blackbox world model is fine, it just needs a reward function.


We now have the freedom to choose whatever policy we want. For instance, we could pick our policy to be 10% random actions, 90% optimal actions and that non of the random actions we choose are overly dangerous.


Hopefully there is some structure to the world, otherwise the number of states times the time to perform an action is going to be massive, maybe too big.
We need tricks to converge with some level of confidence.


### Aside, DYNA

Over time we could build up a picture of the world model, and we could think about what each possible action would do without performing it. A good analogy is dreaming.
So even if the world is not available or it takes a lot of time to perform actions, progress can be made.


### Final Thoughts

The actions we have considered so far are primitive actions such as moving muscles.
We could try to develop more abstract actions, like opening a door that are built up from primitives.

These tiny policies can become allowed actions that only run for a small timeframe.
The issues faced with these tiny policies so far is interruptions, such as mid way through moving a piece on a board the board gets flipped. It is hard to switch nicely into the tiny policy and back.
