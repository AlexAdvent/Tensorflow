# Convolutional Neural Networks With Tensorflow

---
### Goal
In this notebook, we're going to create Convolution Neural Networks with the help of tensorflow Library. we will build and train a CNN from scratch. In this notebook we are use tensorflow library. so lets begin the journey of CNN. 

### Learning Objectives
1.   create CNN network from scratch.
2.   understanding what is convolution.
3.   Train your model and visualize the prediction.

### Getting Started
we will begin by importing some useful packages and the dataset you will use to build and train our model. 

#### MNIST Dataset
The training images our discriminator will be using is from a dataset called [MNIST](http://yann.lecun.com/exdb/mnist/). It contains 60,000 images of handwritten digits, from 0 to 9, like these:


![dataset image](https://miro.medium.com/max/700/1*LyRlX__08q40UJohhJG9Ow.png)



## Convolution Neural Network
### Convolution layer
You will usually hear about 2D Convolution while dealing with convolutional neural networks for images. It is a simple mathematical operation in which we slide a matrix or kernel of weights over 2D data and perform element-wise multiplication with the data that falls under the kernel. Finally, we sum up the multiplication result to produce one output of that operation.


![dataset image](https://miro.medium.com/max/1320/1*LT0l-KXw5FXIkcGVl-KXlQ.gif)
Input shape : (1, 9, 9) — Output Shape : (1, 7, 7) — K : (3, 3) — P : (0, 0) — S : (1, 1) — D : (1, 1) — G : 1

### Max Pooling layer
Max pooling is a pooling operation that selects the maximum element from the region of the feature map covered by the filter. Thus, the output after max-pooling layer would be a feature map containing the most prominent features of the previous feature map.
![dataset image](https://media.geeksforgeeks.org/wp-content/uploads/20190721025744/Screenshot-2019-07-21-at-2.57.13-AM.png)


---

### model summary
![dataset image](https://www.googleapis.com/download/storage/v1/b/kaggle-forum-message-attachments/o/inbox%2F1723677%2F664483930a8dae8d6bdde8521d743b22%2Fimg2.png?generation=1602506057159013&alt=media)

Conv2D layers are convolutions. Each filter (64 in the first  and 128 in the second convolution layers) transforms a part of the image (3*3 for the first two Conv2D layers. The transformation is applied on the whole image.

MaxPool2D is a downsampling filter. It reduces a 2x2 matrix of the image to a single pixel with the maximum value of the 2x2 matrix. The filter aims to conserve the main features of the image while reducing the size.

Dropout is a regularization layer. In our model, 33% of the nodes in the layer are randomly ignores, allowing the network to learn different features. This prevents overfitting.

relu is the rectifier, and it is used to find nonlinearity in the data. It works by returning the input value if the input value >= 0. If the input is negative, it returns 0.

Flatten converts the tensors into a 1D vector.

The Dense layers are an artificial neural network (ANN). The last layer returns the probability that an image is in each class (one for each digit).

As this model aims to categorize the images, we will use a categorical_crossentropy loss function.

---
### confusion matrix
There seems to be a slightly higher confusion between (0,6) and (4,9). This is reasonable as 0's and 6's look similar with their loops and 4's and 9's can be mistaken when the 4's are more rounded and 9's are more angular.

---
### conclusion
Neural Network with convolutional layer has a great impact on accuracy. our model got 99% accuracy with just two convolution layer. Convolutional neural networks (CNNs) have accomplished astonishing achievements across a variety of domains, including medical research, and an increasing interest has emerged in radiology.
