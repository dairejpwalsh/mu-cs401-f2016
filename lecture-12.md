## Really good reference for Gaussian mixture models
[a link](http://www.ee.iisc.ac.in/people/faculty/prasantg/downloads/GMM_Tutorial_Reynolds.pdf)

# Gaussian Mixture Model

A Gaussian Mixture Model (GMM) is a parametric probability density function represented as a weighted sum of Gaussian component densities.

[!Gaussian](/img/lecture-12/graph1.jpg)

A mixture model is a probabilistic model for representing the presence of subpopulations within an overall population, without knowing which 
population it is within. Formally the mixture model corresond to the mixture distribution that represents the probability distribution of 
observations in the overall population.

Some ways of implementing mixture models involve steps that attribute postulated sub-population-identities to individual observations (or 
weights towards such sub-populations), in which case these can be regarded as types of unsupervised learning or clustering procedures.

A Gaussian mixture model is a weighted sum of M component Gaussian densities as given by the equation
[!equation](/img/lecture-12/equation1.gif)

[!equation](/img/lecture-12/equation2.gif)

[!equation](/img/lecture-12/equation3.gif)

If we know the assignments fo the data points to gaussian and the data set and its range, then we can find the parametres of all
k gaussians. Which we can then use to get the highest Probability.

[!Gaussian](/img/lecture-12/graph2.jpg)

[!Gaussian](/img/lecture-12/equation4.gif)

From p(x) we get 
[!Gaussian](/img/lecture-12/equation5.gif)

## EM Step Algorithm for gaussian Mixture Models

We define the EM (Expectation-Maximization) algorithm for Gaussian mixtures as follows. The algorithm
is an iterative algorithm that starts from some initial estimate of Sigma (e.g., random), and then proceeds to
iteratively update Sigma until convergence is detected. Each iteration consists of an E-step and an M-step.
E-Step: Denote the current parameter values as Sigma. Compute wik (using the equation above for membership
weights) for all data points xi
, 1 <= i <= N and all mixture components 1 <= k <= K. Note that for each data
point xi
the membership weights are defined such that PK
k=1 wik = 1. This yields an N * K matrix of
membership weights, where each of the rows sum to 1.
M-Step:
P
Now use the membership weights and the data to calculate new parameter values. Let Nk =
N
i=1 wik, i.e., the sum of the membership weights for the kth component - This is the effective number of
data points assigned to component k

[!Gaussian](/img/lecture-12/equation7.gif)

[!Gaussian](/img/lecture-12/equation6.gif)

[!Gaussian](/img/lecture-12/equation8.gif)

Which is the sum of all points in z_{i} k


