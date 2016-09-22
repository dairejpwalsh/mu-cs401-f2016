## Machine Learning and Neural Networks - cs401 - Barak Pearlmutter

### Lecture 2

**Machine Learning**
 - Supervised
 - Unsupervised
 - Reinforcement Learning
 
[**Reinforcement Learning**](https://en.wikipedia.org/wiki/Reinforcement_learning) -> Very technically difficult

        
![reinforcement learning diagram](http://www.mdpi.com/sensors/sensors-15-06668/article_deploy/html/images/sensors-15-06668-g002-1024.png)
                    


The **World** gives state and rewards (postive or negative) to the **Agent**.
The **World** recieves actions from the **Agent**.

_The objective is to maximize future rewards based on current actions_

##### Games that use reinforcement learning:
- [Chess](https://www.technologyreview.com/s/541276/deep-learning-machine-teaches-itself-chess-in-72-hours-plays-at-international-master/)
- [Go](https://deepmind.com/research/alphago/)    


#### Supervised Learning Algorithms (Regression)

![regression diagram](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Linear_regression.svg/2000px-Linear_regression.svg.png)

##### boiler plate:
- [overfitting](https://en.wikipedia.org/wiki/Overfitting) (high variance can cause overfitting)
- m = number of samples
- dim(x) = n (dimensionality (size) of input)
- x<sup>(i)</sup> this is the i<sup>th</sup> sample not the i<sup>th</sup> derivative
- w = parameters


##### Data

input   ->  output
    
x<sup>i</sup> -> z<sup>(i)</sup> <br>
. <br>
. <br>
x<sup>(m)</sup> -> z<sup>(i)</sup>
    
\vec{z} = f(x;w) = wx + b = w_{1}x + w_{0} = w_{1}x + \theta = [w_{0} w_{1}] \binom{1}{x}


[_Gauss developed a method of finding the squared distance between the data points and the line_](https://en.wikipedia.org/wiki/Carl_Friedrich_Gauss)

The objective is to minimize the sum squared error

![min point](min.jpg)

![linear regression derivative](linear_regression_derivative.jpg)




    
