Paper title: SqueezeNet: AlexNet-level accuracy with 50x fewer parameters


Summary:
The paper proposes novel CNN micro architecture by concentrating on • More efficient distributed training, Less overhead when exporting new models to client and Feasible FPGA and embedded deployment. Correponsdingly the paper points out evidence of googlenet and resnet.
The paper additionally does hyper parameter space exploration for the proposed architecture. It claims such an evaluation is novel which is true owing to design.
The paper implements a single layer with three improvemnts in line with previously mentioned pointers namely Replace 3x3 filters with 1x1 filters, Decrease the number of input channels to 3x3 filters and Downsample late in the network so that convolution layers have large activation maps.

Contrbution:
Fire layer with previously mentioned pointers.
The intution for the same is as mentioned.
	• So that the output activations from 1x1 and 3x3 filters have the same height and width, we
	add a 1-pixel border of zero-padding in the input data to 3x3 filters of expand modules.
	• ReLU (Nair & Hinton, 2010) is applied to activations from squeeze and expand layers.
	• Dropout (Srivastava et al., 2014) with a ratio of 50% is applied after the fire9 module.
	• Note the lack of fully-connected layers in SqueezeNet; this design choice was inspired by
	the NiN (Lin et al., 2013) architecture.
	• When training SqueezeNet, we begin with a learning rate of 0.04, and we linearly
	decrease the learning rate throughout training, as described in (Mishkin et al.,
	2016). For details on the training protocol (e.g. batch size, learning rate, parameter
	initialization), please refer to our Caffe-compatible configuration files located here:
	• The Caffe framework does not natively support a convolution layer that contains multiple
	filter resolutions (e.g. 1x1 and 3x3) (Jia et al., 2014). To get around this, we implement
	our expand layer with two separate convolution layers: a layer with 1x1 filters, and a layer
	with 3x3 filters. Then, we concatenate the outputs of these layers together in the channel
	dimension. This is numerically equivalent to implementing one layer that contains both
	1x1 and 3x3 filters.
Micro arachitecture metaparametrs and squeezeratio , design space exploration.
Trade of 1x1 and 3x3 filters and benefits.
Macro arachitecture analysis with squeezenet and squeezenet with skip connections.


Novel elements:
Fire layer with thre improvements


Failures:
The paper even though does design space exploration but lacks details on arrival of such a formulae
ALso only results are mentioned vs imagenet, which may or may not be true in case of other datasets
Paper is similar to other paper where it doesnt mention any information on how the final network was arrived at.

Notations: Nothing new, easy to follow

Possible explorations/Open Questions:
Skip connection and layer relationship
Results on multiple datasets
Further compression through reduced number of fire layers


Things learnt:
Squeeze layer, alternate design space exploration.


