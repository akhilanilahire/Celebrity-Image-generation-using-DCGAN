# Celebrity Face Generation using Deep Convolutional Generatie Adversarial Networks

This repository contains the implementation of a Deep Convolutional Generative Adversarial Network (DCGAN) for generating high-quality 64x64 pixel images. The project is based on the original GAN paper by Ian Goodfellow et al. and the DCGAN paper by Alec Radford, Luke Metz, and Soumith Chintala.

## Introduction

Generative Adversarial Networks (GANs) are a class of deep learning models introduced by Ian Goodfellow and his colleagues in their seminal paper in 2014. DCGANs are a specific type of GANs that utilize convolutional neural networks (CNNs) in both the generator and discriminator networks. This project focuses on implementing a DCGAN architecture to generate realistic facial images of size 64x64 pixels.

## Model Architecture

### Generator

The generator network takes random noise vectors sampled from a Gaussian distribution as input and synthesizes images. It comprises several transposed convolutional layers followed by batch normalization and ReLU activation functions. The final layer uses a tanh activation function to ensure that the pixel values of the generated images are within the range [-1, 1].

The detailed architecture of the generator is as follows:

- Input: Random noise vector (100-dimensional)
- Transposed Convolutional Layers with Batch Normalization and ReLU Activation
- Output Layer: Transposed Convolutional Layer with tanh Activation (Output size: 64x64x3)

### Discriminator

The discriminator network is a binary classifier that distinguishes between real and fake images. It takes images as input and outputs a probability score indicating the likelihood of the input image being real. The architecture of the discriminator comprises several convolutional layers followed by batch normalization and leaky ReLU activation functions. The final layer uses a sigmoid activation function to produce the probability score.

The detailed architecture of the discriminator is as follows:

- Input: Image (64x64x3)
- Convolutional Layers with Batch Normalization and Leaky ReLU Activation
- Output Layer: Convolutional Layer with Sigmoid Activation (Output size: 1)

## Training

The DCGAN model is trained using the Adam optimizer with a learning rate of 0.0002 and momentum parameters (beta1=0.5, beta2=0.999). During training, the generator and discriminator networks are updated adversarially to improve their performance. The training process involves alternating between updating the discriminator and the generator while adjusting the model parameters to minimize the binary cross-entropy loss.

## Dataset

The CelebA dataset is used for training the DCGAN model. CelebA is a large-scale face attributes dataset with more than 200,000 celebrity images. Each image in the dataset is annotated with 40 binary attributes, such as "Smiling," "Wearing glasses," etc. In this project, we utilize a subset of the CelebA dataset containing aligned and cropped facial images of size 64x64 pixels.

## Results

After training the DCGAN model, it can generate realistic facial images of size 64x64 pixels. The quality of the generated images improves as the training progresses, and the model learns to capture the underlying distribution of the training data. Sample images generated by the trained model can be visualized to evaluate the performance of the DCGAN.

## References

- Ian J. Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron Courville, and Yoshua Bengio. "Generative Adversarial Networks." In Proceedings of the 27th International Conference on Neural Information Processing Systems (NIPS 2014), pp. 2672–2680, December 2014.
- Alec Radford, Luke Metz, and Soumith Chintala. "Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks." arXiv:1511.06434 [cs.LG], November 2015.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
