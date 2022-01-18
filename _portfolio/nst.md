---
title: 'Art Generation using Neural Style Transfer'
excerpt: "Using transfer learning to generate novel artistic images by building deep ConvNets implementing Neural Style Transfer. Used pretrained VGG-19 model for image feature extraction and optimized the content image using cost analysis to obtain desired style.
<br/><img src='/images/nst.jpeg'>"
collection: portfolio 
tags:
  - Transfer Learning
  - VGG-19
  - Cost Analysis
---

  
## Overview
<p align="justify"> Using Artificial Intelligence to turn images into synthetic artworks automatically is a glimpse at the future of synthetic media. Neural Networks are being used to make a simple image into artwork with its particular aesthetic features, defined by swirling shapes and incoherent objects.  </p>

<p align="justify">A CNN based technique, known as Neural style transfer, is an optimization technique used to take two images—a content image and a style reference image (such as an artwork by a famous painter)—and blend them together so the output image looks like the content image, but “painted” in the style of the style reference image. </p> 

<p align="justify">It models the content of a photo as the feature responses from a pre-trained CNN, and further models the style of an artwork as the summary feature statistics. CNN is capable of extracting content information from an arbitrary photograph and style information from a well-known artwork. </p>


## Methodology
<p align="justify">The main aim of NST is for the content in "generated" image G to match the content of "content" image C. For this, I have calculated the content cost function, which is defined as:</p><br>
<img src="http://www.sciweavers.org/tex2img.php?eq=J_%7Bcontent%7D%28C%2CG%29%20%3D%20%5Cfrac%7B1%7D%7B4%20%5Ctimes%20n_H%20%5Ctimes%20n_W%20%5Ctimes%20n_C%7D%5Csum%20_%7B%20%5Ctext%7Ball%20entries%7D%7D%20%28a%5E%7B%28C%29%7D%20-%20a%5E%7B%28G%29%7D%29%5E2%5Ctag%7B1%7D%20%20&bc=White&fc=Black&im=jpg&fs=12&ff=modern&edit=0" align="center" border="0" alt="J_{content}(C,G) = \frac{1}{4 \times n_H \times n_W \times n_C}\sum _{ \text{all entries}} (a^{(C)} - a^{(G)})^2\tag{1}  " width="400" height="44" />
* Here, nH, nW and nC are the height, width and number of channels of the hidden layer, and appear in a normalization term in the cost.
* a(C) and a(G) are the 3D volumes corresponding to a hidden layer's activations.

<p align="justify">and the style cost function, which is defined as:</p><br>
<img src="http://www.sciweavers.org/tex2img.php?eq=J_%7Bstyle%7D%5E%7B%5Bl%5D%7D%28S%2CG%29%20%3D%20%5Cfrac%7B1%7D%7B4%20%5Ctimes%20%7Bn_C%7D%5E2%20%5Ctimes%20%28n_H%20%5Ctimes%20n_W%29%5E2%7D%20%5Csum%20_%7Bi%3D1%7D%5E%7Bn_C%7D%5Csum_%7Bj%3D1%7D%5E%7Bn_C%7D%28G%5E%7B%28S%29%7D_%7B%28gram%29i%2Cj%7D%20-%20G%5E%7B%28G%29%7D_%7B%28gram%29i%2Cj%7D%29%5E2%5Ctag%7B2%7D&bc=White&fc=Black&im=jpg&fs=12&ff=modern&edit=0" align="center" border="0" alt="J_{style}^{[l]}(S,G) = \frac{1}{4 \times {n_C}^2 \times (n_H \times n_W)^2} \sum _{i=1}^{n_C}\sum_{j=1}^{n_C}(G^{(S)}_{(gram)i,j} - G^{(G)}_{(gram)i,j})^2\tag{2}" width="483" height="50" />

* G(S)gram: Gram matrix of the "style" image.
* G(G)gram: Gram matrix of the "generated" image.

<p align="justify"> I optimized the total cost function (linear combination of the above two cost functions) to get pixel values of the image and merged the “content” image (C) and a “style” image (S), to create a “generated” image (G). This generated image is the final output artistic image. I then used pre-trained VGG-19 network to recognize a variety of low level features (at the shallower layers) and high level features (at the deeper layers).</p>


## Technical Details

* Used VGG 19 for feature extraction.
* Used Adam optimizer to minimize the total cost J.
* Learning rate of 0.03.
* Model training requires about 3min on a GPU for 2500 iterations.
* alpha = 10 and beta = 40. alpha and beta are the hyperparameters that control the relative weighting between content and style.


[View Code](https://github.com/KartikSharma907/Art-Generation-with-Neural-Style-Transfer)
</div>  
