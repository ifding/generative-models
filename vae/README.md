
## VAE

- VAE is a neural network that learns to generate its input.
- It can map data to latent space, then generate samples using latent space.
- VAE is combination of autoencoders and variational inference.
- It doesn't work like tradional autoencoders.
- Its output is the parameters of a distribution: mean and variance, which represent a Gaussian-PDF of Z (instead only one value)
- VAE consists of two units: Encoder, Decoder.
- The output of encoder represents Gaussian distributions.(e.g. In 2-D Gaussian, encoder gives 2 mean and 2 variance/stddev)
- The output of decoder represents Bernoulli distributions.
- From a probability distribution, new samples can be generated.
- For example: let's say input x is a 28 by 28-pixel photo
- The encoder ‘encodes’ the data which is 784-dimensional into a latent (hidden) representation space z.
- The encoder outputs parameters to q(z∣x), which is a Gaussian probability density.
- The decoder gets as input the latent representation of a digit z and outputs 784 Bernoulli parameters,  one for each of the 784 pixels in the image.
- The decoder ‘decodes’ the real-valued numbers in z into 784 real-valued numbers between 0 and 1.

### [Understanding and Improving Interpolation in Autoencoders via an Adversarial Regularizer](https://openreview.net/pdf?id=S1fQSiCcYm)

- Unsupervised learning is to uncover the underlying structure of a dataset without using explicit labels.

- A common architecture is the autoencoder: mapping datapoints to a latent code from which the data can be recovered with minimal information loss.

- Typically, the latent code is lower dimensional than the data, which indicates that autoencoders can
perform some form of dimensionality reduction.

- For certain architectures, the latent codes have been shown to disentangle important factors of variation in the dataset which makes such models useful for representation learning.

- In some cases, autoencoders have shown the ability to interpolate. Specifically, by mixing codes in latent space and decoding the result, the autoencoder can produce a semantically meaningful combination of the corresponding datapoints.