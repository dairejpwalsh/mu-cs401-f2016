# Real Systems

Throughout the semester, we have learned various algorithms used in Machine Learning. Real Systems are a combination of such algorithms.

## ImageNet : 2012 Deep convolutional neural network (Alexnet)

ImageNet is a Compute Vision based project which aims to create a database of images with correct annotations. They run an annual contest, where different systems compete to classify and detect objects in images.

Example of a convolutional network: recognising hand-written digits

Classification- invariance to slight movement of the images

Basic level representation, kernel:
![graph1](/img/lecture-24/Kernel.jpg)


The image, after being scanned by the kernel and the weights being added, is convoluted.

This happens multiple times for the same image using the same kernel.

The kernels can change in size-
Smaller kernels- compression

After repeating the process multiple times (for increasingly smaller kernels), the data can be interpreted and a probability distribution can be obtained

Basic level representation, convolution network:
![graph1](/img/lecture-24/Convolution.jpg)




# Alexnet
https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf



## Fooling Neural Networks

Such a neural network can be fooled by creating abstract images that the neural network thinks are in the classification but they are not- Reverse gradient descend
(use image space instead of input space)

Those images are unrecognisable to the human eye, but the neural network will believe with almost 99% certainty that the images are valid and belong to the corresponding class

Check links below for examples of such generated images


# Fooling
http://www.evolvingai.org/fooling
http://www.evolvingai.org/files/DNNsEasilyFooled_cvpr15.pdf

## Possible Solution: Generative models

Setup of the game:
The generative model take in true images as their training set.

The Generator takes in a random vector, and generates false images to feed into the discriminator

The discriminator tries to distinguish between real and fake images.

The trick:  backpropagation through both discriminator and generator, to allow for the generator to create more convincing fake images.

This is an example of an adversarial network: the 2 networks are constantly in battle, constantly improving until the generator produces images indistinguishable from the real ones.

An example of such a network is the deconvolutional network DCGAN (deconvolutional is the inverse of convolution, see link for more info)

Possible use of a Generative Model:
Predicting future frame of a movie based on past frames, thus creating a movie (works well for the first few seconds of the generated movie)

Basic level representation, adversarial network:
![graph1](/img/lecture-24/GenerativeModel.jpg)




# GANs
https://openai.com/blog/generative-models/
https://en.wikipedia.org/wiki/Generative_adversarial_networks
