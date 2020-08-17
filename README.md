# Stanford-Dogs-Classification

# Repository Files


# Project Motivation
As a pet owner, knowing your puppy's breed is important for many reasons. Specific breeds have food limitations and predisposed health issues that you shoud be aware of. Your training methods used on your puppy would also depend on its breed since different breeds have different temperaments. Although you can utilize DNA testing to fulfill this need, such testing can be expensive. Therefore, I am constructing a convolutional neural network that takes in an image of a dog and estimates its breed.

# Project Process
My approach for this project is to follow the OSEMN framework. The steps of this framework is as follow -

Obtain the data
Scrub the data
Explore the data
Model the data
Interpret the data

# Data Source
In this project, I will utilize the Stanford Dogs Dataset which contains 20580 images of 120 dog breeds. Since classifying 120 breeds would be overwhelming for my GPU, I would only use 25 breeds to train my CNN.

# Data Scrubbing
Before training my model, I performed the forming data scrubbing on my images and labels -
1. Resizing images
2. Normalizing pixel intensity values
3. One-hot-encoding of labels
4. Histogram equalization of images
5. Data augmentation of images such as rotation, filling and horizontal flipping

After the scrubbing, the dataset is split into 70% training, 10% validation and 20% testing sets.

# Exploration
The following 5 models were developed and explored in this project. I used the loss and accuracy scores, primarily of the testing data, to measure the models' performances.
1. Base dense neural network
2. Base dense neural network using preprocessed image data
3. Base convolutional neural network
4. AlexNet convolutional neural network
5. VGG16 convolutional neural network

![alt text](https://github.com/kyawsawhtoon/Pump-It-Up/blob/master/Confusion%20Matrix.JPG)
