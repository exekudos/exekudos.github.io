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

<!--more-->

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
