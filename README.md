# ANTsRNet

A collection of well-known deep learning architectures ported to the R language.

## R package dependencies

* [ANTsR](https://github.com/stnava/ANTsR)
* [keras](https://github.com/rstudio/keras) (install from github: ``devtools::install_github( "rstudio/keras")``)
* abind

## Image segmentation

* UNet (2-D, 3-D)
    * [O. Ronneberger, P. Fischer, and T. Brox.  U-Net: Convolutional Networks for Biomedical Image Segmentation](https://arxiv.org/abs/1505.04597)

## Image classification 

* AlexNet (2-D, 3-D)
    * [A. Krizhevsky, and I. Sutskever, and G. Hinton. ImageNet Classification with Deep Convolutional Neural Networks.](http://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)
* Vgg16/Vgg19 (2-D, 3-D)
    * [K. Simonyan and A. Zisserman. Very Deep Convolutional Networks for Large-Scale Image Recognition.](https://arxiv.org/abs/1409.1556)
* ResNet/ResNeXt (2-D, 3-D)
    * [Kaiming He, Xiangyu Zhang, Shaoqing Ren, and Jian Sun.  Deep Residual Learning for Image Recognition.](https://arxiv.org/abs/1512.03385)
    * [Saining Xie and Ross Girshick and Piotr Dollár and Zhuowen Tu and Kaiming He.  Aggregated Residual Transformations for Deep Neural Networks.](https://arxiv.org/abs/1611.05431)
* GoogLeNet (Inception v3) (2-D)
    * [C. Szegedy, W. Liu, Y. Jia, P. Sermanet, S. Reed, D. Anguelov, D. Erhan, V. Vanhoucke, and A. Rabinovich. Going Deeper with Convolutions.](https://arxiv.org/abs/1512.00567)
* DenseNet (2-D, 3-D)
    * [G. Huang, Z. Liu, K. Weinberger, and L. van der Maaten. Densely Connected Convolutional Networks Networks.](https://arxiv.org/abs/1608.06993)

# Misc topics

* Optimizers
* [Blog:  Important papers](https://adeshpande3.github.io/adeshpande3.github.io/The-9-Deep-Learning-Papers-You-Need-To-Know-About.html)
* [Blog:  Intuitive explanation of convnets](https://ujjwalkarn.me/2016/08/11/intuitive-explanation-convnets/)
* [Deep learning book](http://www.deeplearningbook.org)

# To do:

* deconvnet.R
* ResNet and AlexNet use lambda layers so those models aren't writeable to file (h5 format).  So we need to redo to rewrite to json or something else.  At least I think that's the problem. 
* Need to go through and make sure that the 'tf' vs. 'th' ordering is accounted for.  Currently, tensorflow is assumed.  Should work with theano but need to check this.

****************

# My GPU set-up

## Hardware

* Computer 
    * iMac (27-inch, Mid 2011)
    * Processor 3.4 GHz Intel Core i7
    * Memory 16 GB 1333 MHz DDR3 
    * macOS High Sierra (Version 10.13.2)
* GPU
    * [NVIDIA Titan Xp](https://www.nvidia.com/en-us/titan/titan-xp/)
    * [Akitio Node - Thunderbolt3 eGPU](https://www.akitio.com/expansion/node)
    * [Thunderbolt 3 <--> Thunderbolt 2 adapter](https://www.apple.com/shop/product/MMEL2AM/A/thunderbolt-3-usb-c-to-thunderbolt-2-adapter)
    * [Thunderbolt 2 cable](https://www.apple.com/shop/product/MD862LL/A/apple-thunderbolt-cable-2-m)

## Software

* Tensorflow-gpu
* Keras in R
* [NVIDIA CUDA toolkit 9.1](https://developer.nvidia.com/cuda-downloads?target_os=MacOSX&target_arch=x86_64&target_version=1012)
* [NVIDIA CUDA Deep Neural Network library (cuDNN) 7.0](https://www.developer.nvidia.com/cudnn)
* Python 3.6

## Set-up

1. [Put together Titan XP and Aikito node](https://becominghuman.ai/deep-learning-gaming-build-with-nvidia-titan-xp-and-macbook-pro-with-thunderbolt2-5ceee7167f8b)
2. [Install web drivers and GPU support](https://egpu.io/forums/mac-setup/wip-nvidia-egpu-support-for-high-sierra/)
3. [Install tensorflow-gpu](https://medium.com/@fabmilo/how-to-compile-tensorflow-with-cuda-support-on-osx-fd27108e27e1)    
4. [Install keras with tensorflow-gpu](https://keras.rstudio.com)

## Some notes.

* I originally set-up the hardware followed by the drivers (steps 1 and 2) but the tensorflow installation caused some problems.  I believe they were from ``csrutil enable --without kext`` instead of ``csrutil disable`` in step 3 so I ended up using the latter.




