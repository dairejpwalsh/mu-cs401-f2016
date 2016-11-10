#Machine Learning
##Lecture 13

###Expectation-Maximisation (EM) Algorithm:

In the last lecture we covered the EM algorithm. This is based on the probability that a certain piece of data is part of a certain cluster.  

EM Algorithm: ![graph1](/img/lecture-13/lecture13-image1.jpg)

Another way of looking at it: ![graph1](/img/lecture-13/lecture13-image2.jpg)
___

###Exponential Distribution

An exponential distribution is a probability distribution based on the time it takes to reach a certain event. 
Examples of exponential distributions include Radioactive decay and the Lifespan of electronic pieces. 

Exponential distributions are graphed as curves:

Exponential Distribution: ![graph1](/img/lecture-13/lecture13-image3.jpg)

An example: Lets say I give someone a drug and measure how much is left in their system with time. This would usually be an exponential distribution. 

Mixture Models: Both of the distributions below are exponential, but they are based on different time scales. 

![graph1](/img/lecture-13/lecture13-image4.jpg)

---

###Application of EM - Hidden Markov Model (HMM)

Imagine that we have a finite stage: 

(the sytax below means that there is a 70% chance of going from q1 to q3)

 ![graph1](/img/lecture-13/lecture13-image5.jpg)

This machine generates a set of states. We are going to make this into a probability distribution over sequences. 

q(t) = state at time t

So for instance, what would q(17) be?

P(q(17) = 1) = 0  
P(q(17) = 2) = 0 ... 

We could do this 17 times and output the correct state, but this would be inefficient, so how else could this be done? 

#####By using a Markov Model - Sequence of States.

The state the machine is in at time t, depends only on the state we are in at time t-1.
So far we have been focused on general markov models, but a hidden markov model is slightly different.

For a HMM you cannot see the states. You only see the output sybols, which are not in 1:1 correspondance with the states.

In the following diagram, the probability of the output symbols is shown inside the state circles. For example, in q4, there is a 40% chance that H will be the output and a 60% chance that it will be T.

![graph1](/img/lecture-13/lecture13-image6.jpg)

Example of a HMM:  
Say we have a dataset of heartbeats. We don't know what's going on inside the actual heart, we just see the output it has produced. 

####Three main approaches/problems to solve with HMM's:

####1)

o(t) = output symbol at time t

o' = (o(1),o(2),...,o(T))  
λ = all the model parameters

Lets say we have the machine on the previous page and a series of outputs o'.

Whats is: **P(o'|λ)** (Probability of the output sequence given λ)

How do we calculate this efficiently?  
We *could* run the model a million times and see what percentage equal P(0'|λ), but this is very inefficient.  

####2)

Imagine that we have a model of states for the words "the", "cat" and "dog" for speech recognition:

![graph1](/img/lecture-13/lecture13-image7.jpg)

We want to find the sequence of states with max probability given some partictular output and parameters:

**argmax<sub>q'</sub> P(q'|o', λ)**

####3)

Final Problem: Given the output sequence, find the model that produces it (roughly):

**argmax<sub>x</sub> P(λ|o')**

---

*To solve these problems we need to be able to deduce q(t) from q(t+1).*

q' = state sequence  
o' = output sequence

o' = (o(1),o(2),...,o(T))

Initial State Probability: **π(k) = P(q(1) = k)**

Find the probility of going from state q(t) to q(t+1):

**Edges**  
a<sub> i j</sub> = P(q(t+1) = i | q(t) = j)  
A = (a<sub> i j</sub>)

**States**  
b<sub> i</sub> (k) = P(o|t) = (k|q(t) = i)

Example shown below:  
![graph1](/img/lecture-13/lecture13-image8.jpg)



λ = all the model parameters = (π,A,B)

--- 
####*Basic intuition for solving MM:*

Output Sequence: o' = (o(1), o(2),...,o(t-1), o(t), o(t+1),..., o(T))  
Hidden State Sequence: q' =(q(1), q(2),...,q(t-1), q(t), q(t+1),..., q(T))

Say we were only given up to t-1. How would we go about finding the rest? 

o' = (o(1), o(2),...,o(t-1), o(t),..., o(T))  
If we know what state the machine is in at time t, are we able to pump this up to find that state at t+1? Yes we are - discuss next time. 