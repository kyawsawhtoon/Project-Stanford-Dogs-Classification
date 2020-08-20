# Stanford-Dogs-Classification

# Repository Files

The followings are the file you can find in this repository and their descriptions.

**Module 4 - Final Project** - Stanford Dogs Classification.ipynb - Module 4 Final Project's Jupyter Notebook

**Puppy Scanner - Stanford Dogs Dataset.pdf** - High-level presentation of methodology and recommendations for non-technical stakeholders

**README.md** - Descriptions of contents of the repository

**Perfomance Scores.JPG** - Comparison of performance scores of 5 models

**Accuracy Scores.JPG** - Comparison of accuracy scores of 5 models

**Loss Scores.JPG** - Comparison of loss scores of 5 models

**Final Model's Accuracy Score.JPG** - Trend line graph of accuracy score of VGG16 Model

**Final Model's Loss Score.JPG** - Trend line graph of loss score of VGG16 Model

**Italian Greyhound.JPG** - Image of an Italian Greyhound for testing

**Rhodesian Ridgeback.JPG** - Image of a Rhodesian Ridgeback for testing

**Shih Tzu.JPG** - Image of a Shih Tzu for testing

**Italian Greyhound Chart.JPG** - Prediction chart for the Italian Greyhound

**Rhodesian Ridgeback Chart.JPG** - Prediction chart for the Rhodesian Ridgeback

**Shih Tzu Chart.JPG** - Prediction chart for the Shih Tzu

# Project Motivation
As a pet owner, knowing your puppy's breed is important for many reasons. Specific breeds have food limitations and predisposed health issues that you should be aware of. Your training methods used on your puppy would also depend on its breed since different breeds have different temperaments. Although you can utilize DNA testing to fulfill this need, such testing can be expensive. Therefore, I am constructing a convolutional neural network that takes in an image of a dog and estimates its breed.

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

You can find the resulting loss and accuracy scores for each model.
![alt text](https://github.com/kyawsawhtoon/Project-Stanford-Dogs-Classification/blob/master/Performance%20Scores.JPG)

As you can see, VGG16 has the lowest loss scores for both training and testing datasets.
![alt text](https://github.com/kyawsawhtoon/Project-Stanford-Dogs-Classification/blob/master/Loss%20Scores.JPG)

It also has the highest accuracy scores for both training and testing datasets.
![alt text](https://github.com/kyawsawhtoon/Project-Stanford-Dogs-Classification/blob/master/Accuracy%20Scores.JPG)

Thus, I am selecting the VGG16 model as my final model.

# VGG16 Model

My final VGG16 model has the loss score of 1.5213 and accuracy score of 55.18% for the testing data. I believe I can further improve these scores if I train my model for higher number of epochs but it would take a very long time. As you can see below, the loss scores continue to decrease and the accuracy score continue to rise as it was trained longer and longer.

![alt text](https://github.com/kyawsawhtoon/Project-Stanford-Dogs-Classification/blob/master/Final%20Model's%20Loss%20Score.JPG)

![alt text](https://github.com/kyawsawhtoon/Project-Stanford-Dogs-Classification/blob/master/Final%20Model's%20Accuracy%20Score.JPG)

Although 55.18% accuracy is not significant, it is much better than the probability you will get from selecting a dog breed randomly out of 25 breeds.

# Model Testing

To test my final model, I will use the dog images that I found on the internet and feed them into my model. The results are as follow - 

![alt text](https://github.com/kyawsawhtoon/Project-Stanford-Dogs-Classification/blob/master/Italian%20Greyhound.jpg)
![alt text](https://github.com/kyawsawhtoon/Project-Stanford-Dogs-Classification/blob/master/Italian%20Greyhound%20Chart.JPG)

 When I tried an image of an Italian Greyhound, my model predicted it as 46.6% Italian Greyhound. This is quite decent.

![alt text](https://github.com/kyawsawhtoon/Project-Stanford-Dogs-Classification/blob/master/Rhodesian%20Ridgeback.jpg)
![alt text](https://github.com/kyawsawhtoon/Project-Stanford-Dogs-Classification/blob/master/Rhodesian%20Ridgeback%20Chart.JPG)

When I tried an image of a Rhodesian Ridgeback, my model predicted it as 37.2% Rhodesian Ridgeback.

![alt text](https://github.com/kyawsawhtoon/Project-Stanford-Dogs-Classification/blob/master/Shih%20Tzu.JPG)
![alt text](https://github.com/kyawsawhtoon/Project-Stanford-Dogs-Classification/blob/master/Shih%20Tzu%20Chart.JPG)

However, when I used an image of a Shih Tzu, my model predicted 1.6% correctly although it estimated Shih Tzu as one of the top 5 breeds.

# Areas for Improvements

The areas that I can work on in the future to improve my model are -

- Use the entire dataset of 120 breeds. More image data will enhance the predictory power of my model.
- Preprocess the image data further. I could crop the images in order to remove the noises in the image data and only focus on the dogs.
- Add more layers to the VGG16 model in order to see if the new layers can increase the accuracy score.
