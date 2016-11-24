Matrix Decomposition Methods
============================

ICA
---
http://www.cs.cmu.edu/~aarti/Class/10701_Spring14/slides/ICA.pdf


NMF
---

Daniel D. Lee and H. Sebastian Seung (1999),
*Learning the parts of objects by non-negative matrix factorization*,
Nature 401, 788-791 doi:10.1038/44565
http://www.nature.com/nature/journal/v401/n6755/pdf/401788a0.pdf



Hidden Markov Models - Finite state machines
============================================

Problem (1): 
------------
P(sequence of outputs| given λ)

Problem (2): 
------------
Max q' P(q'|o',λ) -> the sequence of states most likely to go through given outputs. 								
			https://en.wikipedia.org/wiki/Viterbi_algorithm
Used in speech recognition

α(t) = P(o(1),o(2)... o(t), q(t)=i|λ)

ß(t) = P(o(t+1)... o(T)|q(t) = i, λ)

Find i that maximises:

max i  αi(t).ßi(t) --> 
 
(P(o',q(t)=i|λ))/(P(o')) = P(q(t) = i|o',λ)

	
Problem (3): 
------------
max λ P(λ|o') -> the parameters of a hidden markov model given output sequence o'

Find λhat such that P(λ'|o')>=P(λ|o')   (equality only holding at local max)

parameters inside λ:

λ = (A, B, π) where A is transition probabilities,
					B is output probabilities,
					π is distribution of start states.

					
αi(t).ßj(t+1).bj(o(t+1)) -> Probability of making a transition from i at time t to j at time t+1 and producing correct output sequence.

Application:
------------

Server System Calls:

There exists a sequence of system calls in a server.
If it is being attacked, the sequence of calls becomes unusual.
Kernel is run normally with an estimate of its HMM.
Kernel recognises if the HMM changes -> Notifies human/restarts server because it believes it is being attacked if the HMM is changed.

Speech Recognition:

If a raw waveform is received from a aeroplane cockpit - one microphone, two pilots. The two pilots can be talking at the same time in this waveform so we need a way of figuring out what each of them is saying. 

If we have two different HMM's, HMM1 AND HMM2 representing the speech of pilot1 and pilot2, then we can create a CrossProduct HMM where each state of this HMM is a pair of states from HMM1 AND HMM2. 

CPstate = (state(hmm1),state(hmm2))  

Graphical Model - graph theory(nodes and arrows)
---------------
General framework for probability distributions


HMM1  

	  q(1) -> q(2) -> q(3) -> .... -> q(T)

		↓		↓		↓				↓
		
	  o(1) -> o(2) -> o(3) -> .... -> o(T)
		
		↓		↓		↓				↓

	  *o(1)*->*o(2)*->*o(3)*-> .... ->*o(T)*	--> Output of combined HMM's

		↑		↑		↑				↑
	
	  o(1) -> o(2) -> o(3) -> .... -> o(T)

		↑		↑		↑				↑
		
      q(1) -> q(2) -> q(3) -> .... -> q(T)
	  
HMM2





Bayes
------

Rain --> GrassWet <-- Sprinklers

In the morning the grass can be wet as a result of two things. It may have rained last night, and/or the sprinklers watered the grass.

The probability that it rained is 1/20. The prob that the sprinklers were on is 1/5.	

If we have a definite observation that the grass was wet then Rain and Sprinklers are no longer independent.

Knowing the grass is wet sets an anti-correlation between Rain and Sprinklers.

Closest solution: Directed graphical model to undirected graphical model. Each node in graph now had a table of energy. Look up all energies and add together.

Undirected graphical model - mapping from states of graph into local terms.  

		













