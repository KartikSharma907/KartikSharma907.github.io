---
title: 'Car Detection using YOLO: You Only Look Once'
excerpt: "I implemented real-time object detection on a car dataset using the YOLO model, which was further improved using a U-net architecture. The YOLO model was stacked with Non-max suppression layers using IOU grid analysis to obtain the most accurate boundary boxes.
<br/><img src='/images/car_detect_yolo.png'>"
collection: portfolio 
tags:
  - Yolo Architechture
  - Object Detection
  - Non-Max Suppression
  - Intersection-over-union
---

## Overview
<p align="justify">Vehicle detection has become an essential component in traffic surveillance and automatic driving. This technology uses computer vision to detect different vehicles in video or real-time via a camera. It finds its applications in traffic control, car tracking, creating parking sensors, number-plate detection, and many more.</p>

<p align="justify">A wide range of computer vision applications has become available for object detection and tracking. Mainly, CNN-based object sensors have made successful and essential steps in detecting objects with the advancement of technology. <b>YOLO</b> ("you only look once") is a popular algorithm because it achieves high accuracy while also being able to run in real-time, almost clocking 45 frames per second.</p>


## Methodology
<p align="justify">Unlike classifier-based approaches, YOLO is trained on a loss function that directly corresponds to detection performance and the entire model is trained jointly. It generates regional predictions to suggest bounding boxes which are then graded, corrected, and their duplicates are removed with the help of IOU grid analysis. Based on the objects detected, it re-scores all the bounding boxes. Finally, the image region with the most significant score is labeled as detected. This algorithm “only looks once” at the image in the sense that it requires only one forward propagation pass through the network to make predictions. I have also incorporated anchor boxes to wisely detect multiple objects lying in a close neighborhood. For each grid cell, I have used 5 anchor boxes and selected the maximum among the probabilty scores of the 80 classes available in COCO dataset (one maximum for each of the 5 anchor boxes).  </p>


## Technical Details

* Language: Python
* The input is a batch of images, and each image has the shape (m, 608, 608, 3).
* The output is a list of bounding boxes along with the recognized classes. 
* The YOLO architecture is: IMAGE (m, 608, 608, 3) -> DEEP CNN -> ENCODING (m, 19, 19, 5, 85).

[View Code](https://github.com/KartikSharma907/Car-Detection-with-YOLO)

