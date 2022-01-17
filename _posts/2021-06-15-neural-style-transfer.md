---
title: 'Art Generation using Neural Style Transfer'
Dated: 2021-06-15
permalink: /posts/2021/06/neural-style-transfer/
tags:
  - Transfer Learning
  - VGG-19
  - Cost Analysis
---

Using transfer learning to generate novel artistic images by building deep ConvNets implementing Neural Style Transfer. Used pretrained VGG-19 model for image feature extraction and optimized the content image using cost analysis to obtain desired style.


## Overview
Since the mid-1990s, the art theories behind the ap-pealing artworks have been attracting the attention of not only the artists but many computer science researchers.There are plenty of studies and techniques exploring how to automatically turn images into synthetic artworks. The process of using CNNs to render a content image in different styles is referred to as Neural Style Transfer (NST).

It models the content of a photo as the feature responses from a pre-trained CNN, and further models the style of an artwork as the summary feature statistics. CNN is capable of extracting content information from an arbitrary photograph and style information from a well-known artwork.


## Methodology
The concept behind Neural Style Transfer is rather than optimizing a cost function to get a set of parameter values for our model network. I optimized the cost function to get pixel values of the image and further merged two images that are “content” image (C) and a “style” image (S), to create a “generated” image (G). This generated image is the final output artistic image. I then used a pre-trained convolutional network like VGG network, VGG-19 to recognize a variety of low level features (at the shallower layers) and high level features (at the deeper layers).


## Technical Details

○ Used VGG 19 for feature extraction.

○ Content cost function is calculated as:


○ Style cost function is calculated as:


○ Total cost is calculated as:


[Code](https://github.com/KartikSharma907/Art-Generation-with-Neural-Style-Transfer)
