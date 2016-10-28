# K-Means Clustering

Maybe the means keep moving around  
### Error Function
We can model the error in our system by:  
![error function](img/lecture-11/error.png)  
The problem with this is that it includes the distance from each mean to each point, but our real error is the sum of distances from each point to the closest mean  
![min error function](img/lecture-11/minerror.png)  


## Batch Algorithm for K-Means
Imagine instead that we had springs from each mean to all the points classified as that type.Then we can define a variable z for each point and mean defined as follows  
![z_ij](img/lecture-11/z_ij.png)  


To update weights we use the formula  
for j =0...  
![weight_change](img/lecture-11/weight_change.png)  
This can be viewed as a two step process:
 * assign to nearest cluster  
 * move cluster centre to middle of points  
This converges in a finite number of iterations as there are only finitely many values for all the z terms so it must converge to some value, even if that is only a local optimum  
invariant: ![sum_zs](img/lecture-11/sum_zs.png)  
However, this is an integer program which is in NP!
We could relax the condition that z_i,j is 0 or 1 to give us a linear program which we can solve to get a probability that each example is in one of the clusters  
![gaussian](img/lecture-11/gaussian.png)  

## [Boltzmann Distribution](https://en.wikipedia.org/wiki/Boltzmann_distribution)
![Boltz1](img/lecture-11/Boltz1.png)  
![Boltz2](img/lecture-11/Boltz2.png)  
![z](img/lecture-11/z.png)  
![E](img/lecture-11/E.png)  




Gaussian = Boltz Distribution over a qudratic bowl.

![sum_distributions](img/lecture-11/sum_distributions.png)    

![max](img/lecture-11/max.png)  
