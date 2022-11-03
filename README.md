## Problem statement:

The aim of this project is to classify people's emotions based on their face images. The need for this project is to build a model that automatically monitors people's emotions and expressions.

There are 2 parts of the project:

Part 1: Need to build a CNN model which can detect 15 key facial points

Part 2: Build a CNN model to detect emotion

## Approach:

### Part 1: Facial key points detection

1.  There were 2140 images given with 15 key facial points to detect (x and y coordinate of each facial point).
2.  Images were given as the string in the csv file along with key facial points, in order to feed these images to NN they were converted into numpy 2d array of shape 96,96
3.  The following image augmentation techniques were applied:
    1.  Image flip horizontally along y axis
    2.  Flipped the key facial points too by subtracting them by 96(width of the image)
    3.  Increase brightness by multiplying pixel values randomly by 1.5 or 2 with clipping of 255
4.  Model build:  
    ![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/b47c6d3a46ab7c6aa21af273771f6bb44d4372c39a0884a2.png)![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/68ae39bbea5e18981e6f43aec346c0bc9cea88fac4bac784.png)
5.  Above model gave accuracy of 74% on the test dataset.

### Part 2: Emotion detection

1.  There were 25k images given in the dataset with following 5 emotions.
    *   0 - Angry
    *   1 - Disgust
    *   2 - Sad
    *   3 - Happy
    *   4 - Surprise
2.  The datasets were a little unbalanced , very few samples were available for Disgust emotion.
3.  Used Tensorflow ImageDataGenerator for augmentation.
4.  Trained NN for 20 epochs with batchsize = 64
5.  Achieved accuracy of 79% on test dataset

### Part 3: Combined both the models for final prediction which will give key facial points along with the emotion in the image.
