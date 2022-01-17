---
title: 'Car Detection using YOLO: You Only Look Once'
excerpt: "Short description of portfolio item number 1<br/><img src='/images/500x300.png'>"
collection: portfolio 
tags:
  - Yolo Architechture
  - Object Detection
  - Non-Max Suppression
  - Intersection-over-union
---


I convolutionally implemented object detection on a car dataset using the YOLO model, which was further modified using a U-net architecture. The YOLO model was stacked with Non-max suppression layers using IOU grid analysis to obtain the most accurate boundary boxes.

## Overview
The detection of vehicles ahead and the traffic conditions while driving are important factors for safe driving, accidental cruising and automatic driving and tracking. Especially real-time perception plays an important role in the development of autonomous vehicles. Therefore, image processing can be used for these purposes.

CNN-based object sensors have made successful and important steps in object detection with the advancement of technology. YOLO is a popular algorithm because it achieves high accuracy whilst also being able to run in real-time.



## Methodology
Conventional CNN networks generate regional predictions to suggest bounding boxes. This is followed by the step of grading, correcting, and removing duplicates of the bounding boxes. It re-scores all bounding boxes based on the objects found. Finally, the region with the highest score on the image is considered as detected. YOLO performs object detection by spatially separated bounding boxes and predicting the entire image with a single neural network.



## Technical Details
○ The input is a batch of images, and each image has the shape (m, 608, 608, 3).

○ The output is a list of bounding boxes along with the recognized classes.

○ The YOLO architecture is: IMAGE (m, 608, 608, 3) -> DEEP CNN -> ENCODING (m, 19, 19, 5, 85).

○ For each of the 19 x 19 grid cells, find the maximum of the probability scores, that is, taking a max across the 80 classes, one maximum for each of the 5 anchor boxes.

○ Select only one box when several boxes overlap with each other and detect the same object using non-max suppression.


[Code](https://github.com/KartikSharma907/Car-Detection-with-YOLO)
