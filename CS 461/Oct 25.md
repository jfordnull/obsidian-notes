# Stochastic State Discovery - Neural Networks and Deep Learning

Attempt at Strong AI through bio-mimicry: Automated, self-directed learning system; Mathematical modeling of neurons

A neuron consists of:
- **Dendrites** receive messages from other cells, resembles branches of tree, attaches to certain receptive components, "receptive field" (nerves in biological systems); Wires that attach to sensors
- The cell body/**soma** is the sum of signals: $\sum$ 
- **Axon** is the conductive "wiring"

Input space vs. Target space

Supervised v. Unsupervised v. Reinforcement learning
- Supervised: a goal/objective function exists
- Reinforcement: We assess good/bad outcomes

Digit example: 16 x 16 pixel array (256) mapped to 0-9

$$f:R^{256}\rightarrow R^{10}$$
Membership as a probabilistic relationship; ratios of likelihood expressed as floats

$$f:R^K\rightarrow R$$
$$z=a_1w_1+...+a_kw_k+b$$
$$a=\sigma(z)$$
a := input, w := weights, b := bias (y-intercept component, shift necessary to center dataset)