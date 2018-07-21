<p align="center">
  <img width="556" height="112" src="https://github.com/ShikharJ/GSoC-2018-Work-Report/blob/master/src/gsoc.png">
</p>

My proposal for **Implementing Essential Deep Learning Modules** was selected as an official project under **Google Summer of Code 2018**. I worked with the organisation [Mlpack](https://github.com/mlpack/), under the mentorship of **Marcus Edel** ([@zoq](https://github.com/zoq)).

## Goal

`Mlpack` is an intuitive, fast, and flexible `C++` machine learning library with bindings to other languages. It is meant to be a machine learning analog to `LAPACK`, and aims to implement a wide array of machine learning methods and functions as a "swiss army knife" for machine learning researchers. In addition to its powerful `C++` interface, mlpack also provides command-line programs and `Python` bindings.

Over the years, Deep Learning has become a promising field of work, attracting attention from the most prominent Machine Learning researchers of the world. One of the most prominent ideas in the field of Deep Learning is `Generative Adversarial Networks` invented by `Ian Goodfellow`. We aimed to implement `GAN`, `Deep Convolutional GAN (DCGAN)` and `Wasserstein GAN (WGAN)`. Some additional goals were also planned, namely the implementation of `Restricted Boltzmann Machines (RBM)`, `Spike and Slab RBM (ssRBM)`, `Stacked GAN (StackGAN)` and `Deep Belief Networks (DBN)`.

## Results

Considering that we were able to meet all our planned goals, and also initiate the work on our additional goals, I'd say we were able to surpass the expectations of the project.

My first task under the official `GSoC` period was to implement the `Transposed Convolutional Layer` along with implementing a number of tests. Next, we also implemented the support for `Layer Normalization` and `Atrous Convolution Layers`. While completing the above tasks, I also uncovered a number of bugs in the implementation of the convolution toolbox, which was fixed alongside these tasks. The biggest milestone of Phase I was undoubtedly the completion of Kris' pending work on the standard `GAN` module, which was merged within a week from the Phase I. 

A lot of heavy lifting was done during Phase II as well. We decided on the idea of using the existing `GAN` module as a base for `DCGAN` and went ahead with directly testing a `DCGAN` network. While we were getting really good results with the stochastic implementations of the above architectures, it took almost ~72 hours for `GAN` and ~90 hours for `DCGAN` to converge on the full `MNIST` datasets. Thereon, we decided to work on optimizing our code for a couple of weeks, and as a result, we added the support for mini-batches in our `GAN` module. This allowed us to bring the training time under ~7 hours! This is almost ~1.5 times the speed of a `Tensorflow` network on the same input! Another major objective we achieved was the implementation of `Wasserstein GAN`, adding both the weight clipping and gradient-penalty variants. The work for optimizer separation was also taken under Phase II, and we were able to wrap up all our planned goals by the end of the second phase itself!

We spent most of our time during Phase III running experiments on different datasets, and implementing the long pending `RBM` and `Spike and Slab RBM` modules. I also spent some time optimizing the `ANN` infrastructure, whih led to a ~30% speedup for the `FFN` and ~22% speedup for the `RNN` networks. I had a few other cool features in mind as well, but probably we'll be working on them after `GSoC` is over.

### Links To Commits

[Mlpack](https://github.com/mlpack/mlpack/commits?author=shikharj)

<p align="left">
  <img width="458" height="193" src="https://github.com/ShikharJ/GSoC-2017-Work-Report/blob/master/src/mlpack.jpg">
</p>

## Pending Pull Requests

[Mlpack](https://github.com/mlpack/mlpack/pulls/ShikharJ)

## Scope and Future Work

Since most of our `GAN` and `Convolutional` toolbox is already quite optimized, and we have really competitive runtimes on single core CPU, probably the next step to take would be to look for alternative methods for faster convolutional training. Some papers can be looked into (suggested by Marcus):

[Deep Tensor Convolution on Multicores](http://proceedings.mlr.press/v70/budden17a.html)

[MEC: Memory-efficient Convolution for Deep Neural Network](http://proceedings.mlr.press/v70/cho17a.html)

We should also explore the idea of parallelizing the `FFN` networks, in order to compare against multi-core benchmarks. At this point, I think that since most of the different `GAN` variants are not significantly different from the standard implementation, more time should be spent on hyper-parameter searching tools (like Kris' ([@kris-singh](https://github.com/kris-singh)) idea of having something similar to [hyperopt](https://github.com/hyperopt/hyperopt)) and `GAN` variants should be given a secondary priority for now.

## Conclusion

I am extremely grateful to my mentor - [Marcus](https://github.com/zoq) - for all his support and for being extremely responsive and helpful everytime I was stuck. Without his help, this project would've been a lot harder and a lot less fun to do.

`Mlpack` was the first Machine Learning library that I contributed to, and the journey has been simply amazing. I have finally come across an Open-Source project that aligns deeply with my personal interests and what I wish to do long-term, a library providing the opportunity of implementing the latest stuff from the research world, a great build architecture and the possibility of working natively in `C++`.

I am also thankful to `Google` for the opportunity to work on this project, which helped me learn a lot in such a short period of time.
