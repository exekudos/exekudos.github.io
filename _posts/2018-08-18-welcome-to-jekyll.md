---
layout: post
title:  "U-Net with SE-ResNet blocks"
categories: [tutorial]
comments: true
---

Squeeze-and-Excitation block (SE-block) was first proposed in the following paper:

https://arxiv.org/pdf/1709.01507v2.pdf

Instead of an equal representation of all channels in a given layer, it suggests developing a weighted representation. The corresponding weights of each channel can be learned in the SE-block.
It introduces an addition hyperparameter, r (ratio) to be used in the SE-block.
For c number of channels, it attempts to learn a (sigmoidal) vector of size c (a tensor of 1x1xc to be exact) and multiplies it with the current tensor in the given layer.

![alt text](https://cdn-images-1.medium.com/max/1600/1*WNk-atKDUsZPvMddvYL01g.png)

Apart from ResNet, SE-blocks can also be implemented in other popular classification models such as Inception and DenseNet.
In this, SE-blocks will be implemented in U-Net, a popular segmentation model.

U-net consists of two segments - a contracting segment followed by an expanding segment. The contracting segment consists of normal CNN operations such as convolutional, activation and pooling whereas expanding segment is composed of deconvolution and upsampling operations.
The standard U-net architecture is given as:

![alt text](http://deeplearning.net/tutorial/_images/unet.jpg)

Replacing each convolution operation with a SE-Resnet block produces an extremely deep architecture which may be useful in some difficult semantic segmentation problems.

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
