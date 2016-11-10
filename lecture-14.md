Let's say we have an election and we know that 1 person in the class votes libertarian.  
We have a blood test that can tell if a person voted libertarian with 95% accuracy.  

If we test one person and get a positive result then what is the probability this person is our libertarian?  

If we test all then with a 0.95 accuracy we get 50*(1-0.95)= 2.5 false positives and 1 true positive.  
Then we can estimate the probability as  
1/(1+2.5) = 1/3.5 = 2/7  

If we want to get a more accurate result then we can use Bayes Rule    

![bayes](img/lecture-14/bayes.png)  

![HMM](http://sites.stat.psu.edu/~jiali/pictures/hmm.gif)  
(in the above they have St, we used qt in lectures)

![alpha](img/lecture-14/alpha.png)  
The whole algorithm runtime is O(tn^2) where n = number of non-zero elements of A  

![beta](img/lecture-14/beta.png)  
Note: Don't implement these yourself, you will run into underflow problems as these probabilities are usually quite small  

One way to get around underflow errors is the store numbers in logged form  
here x, y, z are all logs of the numbers we are dealing with  
z = log(e^x + e^y)  
z = log(e^x(1+e^(y-x)))  
  = loge^x + log(1+e^(y-x))  
  = x + log1p(e^(y-x))  


  
[Hidden Markov Models Cheat Sheet](http://barak.pearlmutter.net/~barak/misc/hmm.pdf)
