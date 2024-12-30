## Overview
Created 2 CNN models that classifies landmarks based on the submission of images, 
- Model 1 is made from scratch, without using transfer learning, it achieves a Test Accuracy of 33%
- Model 2 is made using transfer learning, it achieves Test Accuracy of 79%

## Model Details
### Image transformations
The code performs a series of transformations for the training data, to make sure it extracts enough elements for the training set. it rotates 30 degrees, crops it to 224 pixels, does a horizontal flip and normalizes the images. 
The image size of 224 pixels allows the image to retain a good resolution and capture the main part of any image.

### Architecture description
#### Model 1
The architecture consists in 3 convolutional layers they augment the layers from 3 to 64 layers in order to capture a bigger amount of features of each training image. 
Each layer has a pooling layer to compress the size of the images. 
There are 2 fully connected layers and a dropout of 25%. These layers go from a big size of features 50,176 down to 50.

#### Model 2
The architecture consists in a VGG 16 pretrained model and extracted the features from the 6th layer and froze the features by turning the gradient off.

### Testing results
The model adequately classifies 3 out of 5 submitted images, the 2 that were erroneously classified are not well-known landmarks, which might explain the inaccuracies
