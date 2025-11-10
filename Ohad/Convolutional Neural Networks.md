# Intro
mostly used in computer vision: object detection, medical, face recognition
# Building blocks
## Input
images are a grid of pixels with numeric values. for RGB at each pixel we'll have a list of numbers. this input will be our tensor.
Channel - the i-th member of the tensor.

hierarchial (pixels -> groups -> patterns)

Convolution idea: lets look at a local environment as a feature instead of each pixel on its own. use sliding window, aggregate and create a much smaller input space. 
we run a sliding window with a kernel and aggregate. but the **filter is what is being learned!** 
![[Pasted image 20251109105557.png]]
we see lots of filters there were learned. 

Convolution
$(f*g)=\dots$

non-linear activation function! mostly RELU.

 Pooling
 a kind of [[Regularization]] to keep model simple by reducing size of the output feature map by averaging or maxpooling. 

Deconvnet
instead of image input -> feature map 
we go from feature map -> image input
makes it explainable

# Training CNNs

# Architectures
## LeNet5
## AlexNet
## VGGNet
## GoogLeNet
## ResNet
## ResNeXt
## DenseNet