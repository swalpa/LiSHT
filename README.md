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
<img src="https://latex.codecogs.com/svg.latex?\phi(z)&space;=&space;z&space;\times&space;g(z)&space;\\&space;g(z)&space;=&space;Tanh(z)&space;=&space;\frac{(exp^{z}-&space;exp^{-z})}{(exp^{z}&space;&plus;&space;exp^{-z})}" title="\phi(z) = z \times g(z) \\ g(z) = Tanh(z) = \frac{(exp^{z}- exp^{-z})}{(exp^{z} + exp^{-z})}" />
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

The classification performance of MLP for different activations over Cars Evaluation, Iris and MNIST datasets.

| Dataset   | Activation <br>  Function   | Training |          | Validation |          |
| :-------- | :-------------------------: | :------: | :------: | :--------: | :------: |
|           |                             | Loss     | Accuracy | Loss       | Accuracy |
| Car Eval. | Tanh                        | 0\.0341  | 98\.84   | 0\.0989    | 96\.40   |
|           | Sigmoid                     | 0\.0253  | 98\.77   | 0\.1110    | 96\.24   |
|           | ReLU                        | 0\.0285  | 99\.10   | 0\.0769    | 97\.40   |
|           | Swish                       | 0\.0270  | 99\.13   | 0\.0790    | 97\.11   |
|           | LiSHT                       | 0\.0250  | 99\.28   | 0\.0663    | 97\.98   |
| Iris      | Tanh                        | 0\.0937  | 97\.46   | 0\.0898    | 96\.26   |
|           | Sigmoid                     | 0\.0951  | 97\.83   | 0\.0913    | 96\.23   |
|           | ReLU                        | 0\.0983  | 98\.33   | 0\.0886    | 96\.41   |
|           | Swish                       | 0\.0953  | 98\.50   | 0\.0994    | 96\.34   |
|           | LiSHT                       | 0\.0926  | 98\.67   | 0\.0862    | 97\.33   |
|           | Tanh                        | 1\.1534  | 58\.86   | 1\.3759    | 51\.74   |
|           | Sigmoid                     | 1\.1319  | 59\.51   | 1\.3693    | 52\.12   |
|           | ReLU                        | 1\.1776  | 57\.49   | 1\.3731    | 51\.85   |
|           | Swish                       | 1\.1468  | 58\.65   | 1\.3705    | 51\.83   |
|           | LiSTh                       | 1\.1216  | 59\.13   | 1\.3661    | 52\.16   |
| MNIST     | Tanh                        | 0\.0138  | 99\.56   | 0\.0987    | 98\.26   |
|           | Sigmoid                     | 0\.0064  | 99\.60   | 0\.0928    | 98\.43   |
|           | ReLU                        | 0\.0192  | 99\.51   | 0\.1040    | 98\.48   |
|           | Swish                       | 0\.0159  | 99\.58   | 0\.1048    | 98\.45   |
|           | LiSHT                       | 0\.0127  | 99\.68   | 0\.0915    | 98\.60   |


The classification performance of ResNet for different activations over MNIST and CIFAR-10/100 datasets.

| Dataset   | ResNet  <br>  Depth  | Activation Functions |        |        |        |
| :-------: | :------------------: | :------------------: | :----: | :----: | :----: |
|           |                      | Tanh                 | ReLU   | Swish  | LiSHT  |
| MNIST     | 20                   | 99\.48               | 99\.56 | 99\.53 | 99\.59 |
| CIFAR-10  | 164                  | 89\.74               | 91\.15 | 91\.60 | 92\.92 |
| CIFAR-100 | 164                  | 68\.80               | 72\.84 | 74\.45 | 75\.32 |


The classification performance of LSTM for different activations over twitter140 dataset.

| Dataset    | Activation Functions |        |        |        |
| :--------: | :------------------: | :----: | :----: | :----: |
|            | Tanh                 | ReLU   | Swish  | LiSHT  |
| Twitter140 | 82\.27               | 82\.47 | 82\.22 | 82\.47 |

## Citation

If you use this code or a derivative thereof in your research, we would appreciate a citation to the original paper:

	@article{roy2019lisht,
            title={LiSHT: Non-Parametric Linearly Scaled Hyperbolic Tangent Activation Function for Neural Networks},
            author={Roy, Swalpa Kumar and Manna, Suvojit and Dubey, Shiv Ram and Chaudhuri, Bidyut B},
            journal={arXiv preprint arXiv:1901.05894},
            year={2019}
    }


## License

The code is released under the MIT License. See the attached LICENSE file.

