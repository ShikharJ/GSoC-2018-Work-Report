<p align="center">
  <img width="556" height="112" src="https://github.com/ShikharJ/GSoC-2018-Work-Report/blob/master/src/gsoc.png">
</p>

My proposal for **Implementing Essential Deep Learning Modules** was selected as an official project under **Google Summer of Code 2018**. I worked with the organisation [Mlpack](https://github.com/mlpack/), under the mentorship of **Marcus Edel** ([@zoq](https://github.com/zoq)).

## Goal

`Mlpack` is an intuitive, fast, and flexible `C++` machine learning library with bindings to other languages. It is meant to be a machine learning analog to `LAPACK`, and aims to implement a wide array of machine learning methods and functions as a "swiss army knife" for machine learning researchers. In addition to its powerful `C++` interface, mlpack also provides command-line programs and `Python` bindings.

Over the years, Deep Learning has become a promising field of work, attracting attention from the most prominent Machine Learning researchers of the world. One of the most prominent ideas in the field of Deep Learning is `Generative Adversarial Networks` invented by `Ian Goodfellow`. We aimed to implement `GAN`, `Deep Convolutional GAN (DCGAN)` and `Wasserstein GAN (WGAN)`. Some additional goals were also planned, namely the implementation of `Restricted Boltzmann Machines (RBM)`, `Spike and Slab RBM (ssRBM)`, `Stacked GAN (StackGAN)` and `Deep Belief Networks (DBN)`.

## Results

Considering that we were able to meet all our planned goals, and also initiate the work on our additional goals, I'd say we were able to surpass the expectations of the project.

My first task under the official GSoC period was to implement some additional functionalities for .

### Links To Commits

[Mlpack](https://github.com/mlpack/mlpack/commits?author=shikharj)

<p align="left">
  <img width="458" height="193" src="https://github.com/ShikharJ/GSoC-2017-Work-Report/blob/master/src/mlpack.jpg">
</p>

## Pending Pull Requests

[Mlpack](https://github.com/mlpack/mlpack/pulls/ShikharJ)

## Scope and Future Work

Since most of our `GAN` and `Convolutional` toolbox is already quite optimized, and we have really competitive runtimes on CPU, probably the next step to take would be to look for alternative methods for faster convolutional training. Some papers can be looked into (suggested by Marcus):

[Deep Tensor Convolution on Multicores](http://proceedings.mlr.press/v70/budden17a.html)

[MEC: Memory-efficient Convolution for Deep Neural Network](http://proceedings.mlr.press/v70/cho17a.html)

At this point, I also think that since most of the different `GAN` variants are not significantly different from the standard implementation, more time should be spent on hyper-parameter searching tools (like Kris' ([@kris-singh](https://github.com/kris-singh)) idea of having something similar to [hyperopt](https://github.com/hyperopt/hyperopt)) and `GAN` variants should be given a secondary priority for now.

## Conclusion

I am extremely grateful to my mentor - [Marcus](https://github.com/zoq) - for all his support and for being extremely responsive and helpful everytime I was stuck . Without his help, this project would've been a lot harder and a lot less fun to do.

`Mlpack` was the first Machine Learning library that I contributed to, and the journey has been simply amazing. I have finally come across an Open-Source project that aligns deeply with my personal interests and what I wish to do long-term, a library providing the opportunity of implementing the latest stuff from the research world, a great build architecture and the possibility of working natively in C++.

I am also thankful to `Google` for the opportunity to work on this project, which helped me learn a lot in such a short period of time.
