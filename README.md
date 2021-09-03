# Face-Mask-detection
## Overview:

Covid-19 has spread too fast too much hindering our lives. Wearing a mask is a basic, precautionary measure to prevent the pandemic. This project aims to perform real time face mask detection using DNN face detector and MobileNetV2.

## PART-1

#### Face detection:
##### 1. Using DNN Face detector:
It is a Caffee model based on SSD (Single shot Multibox Detector) and ResNet-10 architecture. It is available in OpenCV.

1. Load network using **cv2.dnn.readNetFromCaffe** passing the weights and layers as arguments. The files for weights and layers are added in the repository (protxt and weights)
Caffe stores and communicates data using blobs.

2. **cv2.dnn.blobFromImage**: cv.dnn.blobFromImage(image[, scalefactor[, size[, mean[, swapRB[, crop[, ddepth]]]]]]) 
Creates 4-dimensional blob from image. Optionally resizes and crops image from center, subtract mean values, scales values by scalefactor, swap Blue and Red channels.
[OpenCV documentation]

This is passed to the network and faces are detected.

## Part2
## Face mask detection using MobileNet:
Training the model:

#### Dataset:
It has 800 images, 400 labelled as with mask and 400 labelled as without mask. The dataset can be downloaded from repository 
(Validation.rar)


**Sample imagesfrom dataset**


![wm](https://user-images.githubusercontent.com/89915293/131957272-16c53ae8-9fcc-4931-9908-0eae27c67a0a.PNG)
![wom](https://user-images.githubusercontent.com/89915293/131957443-776ad519-c221-4287-b218-bb38e60c449e.PNG)



#### Training:
We are loading the MobileNetV2 model from keras and usingits pretrained weights for our basemodel. We have added a few additional layers, following a Dense layer at the end with softmax activation function.

**Results:**![plot_trainvsacc](https://user-images.githubusercontent.com/89915293/131956857-3dbdccfa-f81e-4df0-9634-03ee5cf5846b.PNG)

97.03% accuracy was achieved on training data. This can be augmented with our face detection model in order to get the Face Mask Detection.

Output on test video from youtube:

![op](https://user-images.githubusercontent.com/89915293/131958232-6299d7e7-9434-420f-b0c6-8d3ea7f8a025.PNG)
![output](https://user-images.githubusercontent.com/89915293/131958235-e1359294-a455-42bf-a9eb-fca2e12829e3.PNG)
![output2](https://user-images.githubusercontent.com/89915293/131958248-5b838af0-15ba-4d1e-8834-f57bf8907e3e.PNG)

Limitations:

Due to occlusion in some cases, our face detector isnt able to detect faces.
















