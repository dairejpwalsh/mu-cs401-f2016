# Correlation vs Casuality

Propose the statement that people who drink coffee are likely to have a stroke. 
To determine if this statement is true then we first measure the population and then 
we calculate the Probobility of people having a stroke and Probability of people
who have strokes and also drink coffee.
[!Probility of C/S](/img/lecture-10/prob1.gif)

Where P=: Probability, C:= is the people who drink coffee, S:= is people who have strokes

So is the probability of people who drink coffee and have strokes less then the
probablility of people who drink coffee
Q: [! Prob of C|S](/img/lecture-10/prob2.gif)

## Baye's Rule 
In probability theory and statistics, Bayes' theorem escribes the probability of an event,
based on conditions that might be related to the event.
[! Bayes Rule](/img/lecture-10/baye.gif)

For example, In our case if drinking coffee is related to having strokes, then, using Bayes’
theorem, a person's consumption of coffee can be used to more accurately assess the probability 
that they may have a stroke.
And so,
[! Prob of C|S](/img/lecture-10/prob3.gif)
[! Prob of C|S](/img/lecture-10/prob4.gif)
[! Prob of C|S](/img/lecture-10/prob5.png)
[! Prob of C|S](/img/lecture-10/prob6.png)
[! Prob of C|S](/img/lecture-10/prob7.png)

And so people who drink coffee and people who have strokes are independent.

--

M - Model
D - data

To get the most likely right answer to a given problem.

[! Prob of C|S](/img/lecture-10/prob8.png)

The general model is a function with input x gives us a output y
How likely is a function to give us the exact y we want for our problem.

K - means clustering falls under unsupervised learning.The data points which are supposed to be 
treated as noise are also considered in clusters. If k = 1  we still produce noise however in each
case our noise is treated in Gaussian terms.

If K-means clustering produces output y then our
1-means clustering produces [! yhat](/img/lecture-10/yhat.gif)

[! sum1](/img/lecture-10/sum1.gif)

[! Prob of C|S](/img/lecture-10/prob9.gif)

[! Prob of C|S](/img/lecture-10/prob10.gif)
[! Prob of C|S](/img/lecture-10/prob11.gif)

Note that the probibility to get the right answer from the data using our model will be quite small as it 
is being multiplied by probibilities (fractions)

[! Prob of C|S](/img/lecture-10/prob12.gif)

Gaussian (0;1) ~ y
[! Prob of C|S](/img/lecture-10/prob13.gif)

[! Prob of C|S](/img/lecture-10/prob14.gif)

Cancel the log expression with the denominator of the exponent

[! Prob of C|S](/img/lecture-10/prob15.gif)

Then differentiate with respect to omega
[! Prob of C|S](/img/lecture-10/prob16.gif)

solve for omega
[! Prob of C|S](/img/lecture-10/prob17.gif)

[! Prob of C|S](/img/lecture-10/prob18.gif)

To Convert our problem from 1-means clustering to k-means clustering we change the model to from 1 omega to 
k amount omega's
