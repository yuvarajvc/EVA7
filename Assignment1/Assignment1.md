Channels and Kernels (according to EVA):

Channels:

Channels depends on the type of image we use during image detection. If the image used is grey scale then the number of channels is 1. Similarly if the image used is of color variant, mostly of RGB then the number of channels would be 3 (red, green and blue channels)

Channels are like feature bags which hold similar information. Each channel among RGB will hold similar information with respect to each other and this information is kept separate from each channel. By keeping the information separate we can use Red channel to detect how much red color is falling on a particular pixel at a particular location. Thereby channels store specific information and transmit to the layers above.

Kernels:

Kernels can be considered as filters or feature extractors. Kernels are used to detect the features from an image like edge detection, blurring the images or sharpening the images, sharpening the images with appropriate weights in kernel. Using kernel we can reduce the noise on the images which helps in detecting more features and hence differentiating the images.

Kernel is a small matrix of numbers applied across an image in order to capture the features of an image. This kernel is applicable on all the channels of the image separately and the image information of those channels is passed on to the next layer.

Channels are part of the image while the kernels are the feature extractors applied onto an image in order to extract the information specific to image and specific to each channel.

Why should we (nearly) use 3x3 Kernels?

The most important reason we use the 3x3 kernel mostly is that its useful to get lower number of weights and more number of layers. Having less weights results in computational efficiency and having more layers results in learning more complex and non-linear features.

3x3 kernel can be used to extract the parts of the image in order to reduce the total dimension of the image in next layer. At each layer there will be some features that are extracted.

**How many times do we need to perform 3x3 convolutions operations to reach close to 1x1 from 199x199 **

We need to perform 3x3 convolution 99 times in order to reach 1x1 from 199x199.

Below is the reduction in size from 199x199 to 1x1

199x199>197x197>195x195>193x193>191x191>189x189>187x187>185x185>183x183>181x181>179x179>177x177>175x175>173x173>171x171>169x169>167x167>165x165>163x163>161x161>159x159>157x157>155x155>153x153>151x151>149x149>147x147>145x145>143x143>141x141>139x139>137x137>135x135>133x133>131x131>129x129>127x127>125x125>123x123>121x121>119x119>117x117>115x115>113x113>111x111>109x109>107x107>105x105>103x103>101x101>99x99>97x97>95x95>93x93>91x91>89x89>87x87>85x85>83x83>81x81>79x79>77x77>75x75>73x73>71x71>69x69>67x67>65x65>63x63>61x61>59x59>57x57>55x55>53x53>51x51>49x49>47x47>45x45>43x43>41x41>39x39>37x37>35x35>33x33>31x31>29x29>27x27>25x25>23x23>21x21>19x19>17x17>15x15>13x13>11x11>9x9>7x7>5x5>3x3>1x1

How are kernels initialized?

Kernels are initialized randomly at the beginning. Gradually the kernels are updated during training using a process called back propagation which uses the optimizers to calculate gradients. Weights for the kernel varies based on the feature and also the brightness of the image background. Based on calculation of the weights the image background also can be obtained as plain white colour or dark black based on the requirement.

What happens during the training of a DNN?

During the training of a DNN every neuron is connected to the neurons in the previous layer making, thus making it densely connected.

Below is the architecture of the DNN

img

Above image represents the neural network with one hidden layer. If we consider the hidden layer as the dense layer the image can represent the neural network with a single dense layer.

Once the input layer is defined we need not define input layer for every dense layer.

Drawbacks:

Dense layer is an input layer because after calling the layer we can not change the attributes because as the input shape for the dense layer passes through the dense layer the Keras defines an input layer before the current dense layer.
Due to fully connected layers the complexity will increase and hence we need good computation power to carry out DNN.
