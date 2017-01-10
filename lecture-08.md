# Perceptrons 
----------
In machine learning, the perceptron is an algorithm for supervised learning of binary classifiers
(functions that  can decide whether an input, represented by a vector of numbers, belongs or not
to some specific class)

Perceptrons gained lots of interest in the 60's

An Example of a Perceptron 
Graph to determine if you will fall.
The x and y co-ordinates are the positions of both feet on the ground.
If both feet are either foward or back together than it will be determined that you will fall.
If one foot is foward and the other foot is behind the less likely a person will fall.

## Linear Discriminators 
With a vector x against multiple vectors, the angles between these vectors is some Theta Î of which
we obtain the final output Sigma.
To which they are only two types of Sigma, Hard and Soft.
![Hard and Soft Sigma](/img/lecture-08/Sigma.png)  

The more Softer the sigma is, the more differentiable it is.
The Vector X is the input and the output is Sigma.

## Problem: Family Tree
![Family tree](/img/lecture-08/relationship.png)

A Machine Learning program was developed in the early 80's and 90's that would follow the structure
of the tree and create a generalization of the relationship.

## ALVINN

ALVINN (Autonomous Land Vehicle In a Neural Network)is a perception system which learns to control 
the NAVLAB vehicles by watching a person drive. ALVINN's architecture consists of a single hidden 
layer back-propagation network. The input layer of the network is a 30x32 unit two dimensional 
'retina' which receives input from the vehicles video camera. Each input unit is fully connected
to a layer of five hidden units which are in turn fully connected to a layer of 30 output units. 
The output layer is a linear representation of the direction the vehicle should travel in order to 
keep the vehicle on the road.
To drive the vehicle, a video image from the onboard camera is injected into the input layer. 
Activation is passed forward through the network and a steering command is read off the output layer.
The most active output unit determines the direction in which to steer.

To teach the network to steer, ALVINN is shown video images from the onboard camera as a person drives,
and told it should output the steering direction in which the person is currently steering. The back-propagation
algorithm alters the strengths of connections between the units so that the network produces the
appropriate steering response when presented with a video image of the road ahead of the vehicle.
After about 3 minutes of watching a person drive, ALVINN is able to take over and continue driving on its own.

Because it is able to learn what image features are important for particular driving situations, 
ALVINN has been successfully trained to drive in a wider variety of situations than other autonomous 
navigation systems which require fixed, predefined features (like the road's center line) for accurate driving.
![ALVINN](/img/lecture-08/alvinn.png)


The Video Input Retina is the source of the collection of the data. While the road intensity is the
data, however between the data set of the road is not enough to drive ALVINN. In the ALVINN.png there
are Hidden Units within the data set. These Hidden Units are the Anomilies that ALVINN will need to 
detect on any given random road. These include obstacles are car would face such as bumps.

## Interpolation vs Extorpolation
Interpolation is guessing data points that fall within the range of the data you have, i.e. 
between your existing data points. Extrapolation is guessing data points from beyond the range of your 
data set.
Interpolation - easy
Extrapolation - hard

## Pep smear 
* An approach to detecting Cancer cells
* Gain skin cells, stain them, Then we can detect a cancer cell
* However cells will possibly develop into cancer cells.
* Previous Pep smear screenings were used to see the change from non-cancer to cancer cells
* Machine Learning techniques were used to categorise these cells - didnt work
* New approach was to scan cells
* Give the cell a score 
* Then give them to human technician based on score 
* Human technician can now more easily detect more potential treats and discard the faulty cells easily that passed
* Combination of both machine learning and human intuition needed to reduce problem

## Recurent Nueral Network 
A recurrent neural network (RNN) is a class of artificial neural network where connections between units 
form a directed cycle. This creates an internal state of the network which allows it to exhibit dynamic temporal behavior.

![RNN Handwriting generator](/img/lecture-08/rnn.jpg)

RNN Handwriting generator
The vector x is given the data set s where s is the x,y coordinates of the position of the pen.
After each iteration fo the new data set it takes a weighted average and produces the output O
The unfolding of this process is done recursively shown in the diagram. (W -> s(t) -> s(t+1))

## Cross Validation Error 
In k-fold cross-validation, the original sample is randomly partitioned into k equal sized subsamples. Of the k subsamples,
a single subsample is retained as the validation data for testing the model, and the remaining k - 1 subsamples are used
as training data.

Cross Validation error memorises a feature in the data set.
It is a model validation technique for assessing how the results of a statistical analysis will generalize to an independent data set.
![cross validation error](/img/lecture-08/cross-valid.png)



In order to avoid overtraining, the most robust method is cross validation error




