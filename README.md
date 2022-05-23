# automatic-image-brightness-adjustment
An automatic adjustment model is developed for brightness adjustment in images.


This repository contains the training of a model to automatically adjust the brightness of the photographs given a given dataset. 

## Problema
A photography studio has thousands of photographs that they take at different events: concerts, conferences, shows, public events, etc. Some photographs are too dark or too bright, so they have to spend time manually adjusting the brightness to an optimal level, by hand, wasting many hours and a lot of precious time that could be spent editing the image in a more interesting way. The studio provides you with a data set with thousands of images that have already been adjusted for brightness, your job is to provide a way to automatically adjust the brightness for new images for the studio.

## Dataset
The dataset consists of 8758 images of 128 px x 128 px in RGB format.
[Dataset](https://www.kaggle.com/code/shruthimshruthim/google-scrapped-image/data?select=images) 


If you want to review the training see this [notebook](#) , if you just want to play with the neural network see this [notebook](#).

## Background information

Different methodologies have been proposed to improve the basic parameters of an image, for example, contrast can be improved with histogram equalization (HE). However, it does not always give satisfactory results. Other techniques such as brightness preserving histogram equalization (BBHE), dualistic subimage equalization (DSHE), and minimum mean brightness error histogram equalization (MMBEBHE) have been proposed as methods before applying HE. However, these techniques do not always achieve the desired enhancement, plus the editing parameters are set to a proposed standard rather than a dataset. So exploration in the field of AI to solve this problem is promising.

## Proposals

Given the problem can be approached from 3 different points and evaluate the efficiency:

**1) Multilayer conv perceptron for V search in HSV images [notebook](#).**

**2) Autoencoder conv for V recreation in HSV images [notebook](https://github.com/toledoangel/automatic-image-brightness-adjustment/blob/main/Autoencoder.ipynb).**

**3) Convolutional neural networks **

Given the time to perform this task, in this repository we chose to follow option 1 by contrasting it with an aggregate of conv


### 1) Multilayer conv perceptron for V search in HSV images.

#### Image preprocessing

The images of the set are considered to be edited and in their final form, so to create the dataset for each image the light value (V of HSV) was edited randomly in a range between 0.1 to 1.9 without considering the 1.


#### Training 

For training the dataset was separated into 70% training 30% test. The training was performed with 200 epochs, and a batch size of 10. The input consists of the image in HSV and the gamma value that was modified in V. The training was performed in Google Colab. 

#### Results 

The results are favorable with an image output very close to the desired one, giving an accuracy of 60% comparing original RGB image vs. RGB inference.  

#### Comments.

I was working on contrasting the multilayer perceptron vs. an autoencoder model that can be found in this notebook, however no optimal autoencoder outputs were obtained yet to compare. 
In the end to improve the application you can compare a model obtained by multilayer perceptron vs autoencoder vs a combination of both.

