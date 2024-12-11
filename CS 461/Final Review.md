# Neural Networks

**Loss Functions**

# Activation Functions

Activation function defines the output of a node (or neuron). They introduce non-linearity into the model, allowing it to learn complex (non-linear) data. Without them, NN would be a linear function.

(More neurons improve representation, but may overfit to training data.)

**Sigmoid** ($\sigma$):
$$\sigma(x)=\frac{1}{1+e^{-x}}$$
- Takes a real-valued number and squashes it between 0 and 1
	- Output comparable to biological neuron (0 = not firing, 1 = firing)
	- Output approaching 0 or 1 is called neuron *saturation*
		- Has the effect of a *vanishing gradient* problem; gradient at these regions is almost zero. Therefore network loses ability to learn new patterns, learns *very slowly*. (Gradients become negligible during back propagation.)
- Function has "S"-shaped curve
- Differentiable (i.e. suitable for back propagation)

**Tanh**:
$$tanh(x)=\frac{2}{1+e^{-2x}}-1$$
- Like sigmoid, tanh neurons have a saturation problem. Tanh is a scaled sigmoid function: $tanh(x)=2\cdot \sigma(2x)-1$ 
- Unlike sigmoid, the output is zero-centered. For this reason we prefer it

**Representational Power**:

NNs with at least one hidden layer are *universal approximators*. (UAT) I.e., NNs can approximate any arbitrary complex continuous function, provided error is nonzero. Error can be made arbitrarily small but not zero.

**Computer Vision and "Deep Learning" - Convolutional Neural Networks (CNNs)**:
- Designed to process grid structures like an image, by using convolutional layers to detect spatial patterns. Useful for large data. A convolutional filter slides (convolves) across an image/input matrix. E.g. edge detection is a common form of feature extraction.
- Hidden units in a layer are only connected to small region of layer before it called the *receptive field*
- *Feature Map* depth corresponds to number of convolutional filters used at each layer. CNNs can be used to detect rich feature hierarchies/abstractions. E.g. pixel -> edge -> texture -> object
- Efficient to train. Allow parameter sharing. Thus less parameters than NNs


# Knowledge Representations