# Denoising-Autoencoder-cifar-10
Implemented a denoising algorithm on cifar-10 dataset.

### Dataset:

The CIFAR dataset consists of 60,000  RGB images of 32x32 pixels having objects from 10 classes. The dataset is divided into 6 batches, each comprising 10,000 images. Out of the total batches, 5 batches are used for training and one for testing.
After loading the dataset, we normalized it into float values between 0-1 and then added Gaussian noise with mean = 0 and standard deviation = 0.1 to produce noisy data.

### Architecture:

The model used is an autoencoder whose architecture is inspired by U-Net. Unlike the general convolutional neural networks, U-net is designed to handle strong noise in the images.
Autoencoder consists of two blocks, the convolutional block, and the deconvolutional block.
These blocks perform three operations: 2-D convolution, Batch normalization, and ReLU Activation.
The model has 4 convolutional blocks with downsampling, 1 convolutional block without downsampling, 4 deconvolutional blocks with upsampling, interleaving concatenations, 1 final deconvolution that recreates image size to (32, 32, 3), and 1 activation layer with sigmoid that scales values to 0-1.

### Training:

Training is carried out for 100 epochs with mini-batches of 128 images. Loss is calculated by Mean Squared Error and the training is optimized using Adam optimizer. 

### Evaluating the model:

To evaluate how the trained model rendered clear images from input noisy images, we calculated the mean squared error of the whole cifar10 dataset. To finally test the performance of the model on the unseen data,  the output for the test data is observed and the corresponding test loss and accuracy is measured.

### Result

![Optional Text](../master/myFolder/image.png)


References:
http://stanford.edu/class/ee367/Winter2019/dua_report.pdf
