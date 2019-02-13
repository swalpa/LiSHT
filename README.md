# LiSHT
This repository contains a Keras implementation of the paper "LiSHT: Non-Parametric Linearly Scaled Hyperbolic Tangent Activation Function for Neural Networks" - ([link to the arXiv page](https://arxiv.org/abs/1901.05894))

    Roy, Kumar S., Manna, S., Dubey, Ram S., and Chaudhuri, Baran B., 2019. LiSHT: Non-Parametric Linearly Scaled 
    Hyperbolic Tangent Activation Function for Neural Networks. arXiv preprint arXiv:1901.05894.
            
            
## Description
The  activation function in neural network is one of the important aspects which facilitates the deep training by introducing the non-linearity into the learning process. However, because of zero-hard rectification, some the of existing activations function  such as ReLU and Swish miss to utilize the negative input values and may suffer from the dying gradient problem. Thus, it is important to look for a better activation function which is free from such problems. As a remedy, this paper proposes a new non-parametric function, called Linearly Scaled Hyperbolic Tangent (LiSHT) for Neural Networks (NNs). The proposed LiSHT activation  function is an attempt to scale the non-linear Hyperbolic Tangent (Tanh) function by a linear function and tackle the dying gradient problem.

<img src="assets/Activations.png"/>

## What is a LiSHT?

Most neural networks work by interleaving linear projections and simple (fixed) activation functions, like the ReLU function:

<p align="center">
<img src="https://latex.codecogs.com/svg.latex?g(s)&space;=&space;\max&space;\left(&space;0,&space;s&space;\right&space;\)&space;\,." title="φ(z) = \max \left( 0, z \right \) \,." />
</p>

A LiSHT is instead a parametric activation function defined as non-parametric approximator:

<p align="center">
<a href="https://www.codecogs.com/eqnedit.php?latex=\φ(z)&space;=z·g(z)~~~and~~&space;g(z)&space;=&space;Tanh(z)&space;=&space;(exp^{z}-&space;exp^{-z})/(exp^{z}&space;&plus;&space;exp^{-z})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?φ(z)&space;=z·g(z)and&space;g(z)&space;=&space;Tanh(z)&space;=&space;(exp^{z}-&space;exp^{-z})/(exp^{z}&space;&plus;&space;exp^{-z})" title="φ(z) =z·g(z)and g(z) = Tanh(z) = (exp^{z}- exp^{-z})/(exp^{z} + exp^{-z})" />
</a>
</p>


## Pre-Activation ResNet

<img src="assets/Pre-resnet.png"/>

## Experimental Data
 
 The effectiveness of the proposed LiSHT activation function is evaluated on six benchmark datasets:
 
 - [Car Evaluation Dataset](https://archive.ics.uci.edu/ml/datasets/car+evaluation)
 - [Iris Flower Dataset](https://archive.ics.uci.edu/ml/datasets/iris)
 - [MNIST Dataset](http://yann.lecun.com/exdb/mnist/)
 - [CIFAR-10 Dataset](https://www.cs.toronto.edu/~kriz/cifar.html)
 - [CIFAR-100 Dataset](https://www.cs.toronto.edu/~kriz/cifar.html)
 - [Twitter140 Dataset](https://www.kaggle.com/kazanova/sentiment140)
 
 <img src="assets/data.png"/>

## Results


## Citation

If you use this code or a derivative thereof in your research, we would appreciate a citation to the original paper:

	@article{roy2019lisht,
            title={LiSHT: Non-Parametric Linearly Scaled Hyperbolic Tangent Activation Function for Neural Networks},
            author={Roy, Swalpa Kumar and Manna, Suvojit and Dubey, Shiv Ram and Chaudhuri, Bidyut B},
            journal={arXiv preprint arXiv:1901.05894},
            year={2019}
    }
