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
max αi(t).ßi(t) -->
 i 
 
P(o',q(t)=i|λ)
______________ = P(q(t) = i|o',λ)
	P(o')
	
Problem (3): 
------------
max λ P(λ|o') -> the parameters of a hidden markov model given output sequence o'

Find λhat such that P(λ'|o')>=P(λ|o')   (equality only holding at local max)

parameters inside λ:
λ = (A, B, π) where A is transition probabilities
					B is output probabilities
					π is distribution of start states

					
αi(t).ßj(t+1).bj(o(t+1)) -> Probability of making a transition from i at time t to j at time t+1 and producing correct output sequence.

Application:
------------
There exists a sequence of system calls in a server.
If it is being attacked, the sequence of calls becomes unusual.
Kernel is run normally with an estimate of its HMM.
Kernel recognises if the HMM changes -> Notifies human/restarts server because it believes it is being attacked if the HMM is changed.

