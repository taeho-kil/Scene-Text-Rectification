# Scene text rectification using glyph and character alignment properties


<p align="center">
<img src="/algorithm_image/abs.png" width="700"> 
</p>

## Abstract

Scene text images usually suffer from perspective distortions and hence their rectification has been
an essential pre-processing step for many applications. Existing methods for scene text rectification
mainly exploited the glyph property, which means that the characters in many languages have horizontal
/vertical strokes and also some symmetric shapes. We propose to use an additional
properties that the characters need to be well aligned when rectified. Specifically, we propose a new
method based on the cost function optimization which explicitly imposes alignment constraints on
the rectified results. For this, character alignment as well as glyph properties are encoded in the proposed
cost function, and its minimization generates the transformation parameters. For encoding the
alignment constraints, we perform the character segmentation using a projection profile method before
optimizing the cost function. Since better segmentation needs better rectification and vice versa,
the overall algorithm is designed to perform character segmentation and rectification iteratively. We
evaluate our method on real and synthetic scene text images and the experimental results show that
our method achieves higher OCR rate than the previous approaches and also yields visually pleasing
results.


## Algorithm

First, we extract character components by using character segmentation, then we perform the text rectification by aligning the top and bottom points of all extracted characters. Better segmentation needs better rectification and vice versa, then we perform them iteratively.

<p align="center">
<img src="/algorithm_image/alg1.png" height="120"> <img src="/algorithm_image/alg2.png" height="120"> 
</p>

### Character segmentation

We extract character components using a projection profile method, and separate characters 
with the projection value of more than mean stroke with value.

<p align="center">
<img src="/algorithm_image/seg1.png" height="80">
<img src="/algorithm_image/seg2.png" height="120"> 
</p>

### Text rectification

Alignment of characters represents following two properties that are vertical and horizontal 
alignment properties. The vertical alignment means that characters in the undistorted text 
are aligned to the horizontal-straight lines, specifically the most top and bottom points of
characters are on one of two lines. The horizontal alignment means that the character widhts of 
undistorted text have minimal values. 
We perform text rectification by using two alignment properties.

<p align="center">
<img src="/algorithm_image/align_vert.png" width="350">
<img src="/algorithm_image/align_hori.png" width="380"> 
</p>
<p align="center">
vertical & horizontal alignment properties
</p>

<p align="center">
<img src="/algorithm_image/rectify.png" width="700">
</p>
<p align="center">
rectification using alignment properties
</p>

## Experimental results
### Scene text dataset
We evaluate our method on the scene text dataset [2], that is consisted of real and synthetic text images. 
They are binarized text images and include English and Chinese characters.
<p align="center">
<img src="/algorithm_image/dataset.png" width="350">
</p>

### Rectified text images
## real scene text images
| Input image   |    TILT [1]   |   Proposed    |
| ------------- | ------------- | ------------- |
| <img src="/results/real_scene/1_in.jpg" width="100">  | <img src="/results/real_scene/1_TILT.png" width="100">  | <img src="/results/real_scene/1_proposed.png" width="100">  |
| <img src="/results/real_scene/2_in.jpg" width="100">  | <img src="/results/real_scene/2_TILT.png" width="100">  | <img src="/results/real_scene/2_proposed.png" width="100">  |
| <img src="/results/real_scene/3_in.jpg" width="100">  | <img src="/results/real_scene/3_TILT.png" width="100">  | <img src="/results/real_scene/3_proposed.png" width="100">  |
| <img src="/results/real_scene/4_in.jpg" width="100">  | <img src="/results/real_scene/4_TILT.png" width="100">  | <img src="/results/real_scene/4_proposed.png" width="100">  |
| <img src="/results/real_scene/5_in.jpg" width="100">  | <img src="/results/real_scene/5_TILT.png" width="100">  | <img src="/results/real_scene/5_proposed.png" width="100">  |
| <img src="/results/real_scene/6_in.jpg" width="100">  | <img src="/results/real_scene/6_TILT.png" width="100">  | <img src="/results/real_scene/6_proposed.png" width="100">  |
| <img src="/results/real_scene/7_in.jpg" width="100">  | <img src="/results/real_scene/7_TILT.png" width="100">  | <img src="/results/real_scene/7_proposed.png" width="100">  |
| <img src="/results/real_scene/8_in.jpg" width="100">  | <img src="/results/real_scene/8_TILT.png" width="100">  | <img src="/results/real_scene/8_proposed.png" width="100">  |
| <img src="/results/real_scene/9_in.jpg" width="100">  | <img src="/results/real_scene/9_TILT.png" width="100">  | <img src="/results/real_scene/9_proposed.png" width="100">  |
| <img src="/results/real_scene/10_in.jpg" width="100">  | <img src="/results/real_scene/10_TILT.png" width="100">  | <img src="/results/real_scene/10_proposed.png" width="100">  |

## synthetic text images
| Input image   |    TILT [1]   |   Proposed    |
| ------------- | ------------- | ------------- |
| <img src="/results/synthetic/1_in.bmp" width="400">  | <img src="/results/synthetic/1_TILT.png" width="400">  | <img src="/results/synthetic/1_proposed.png" width="400">  |
| <img src="/results/synthetic/2_in.bmp" width="400">  | <img src="/results/synthetic/2_TILT.png" width="400">  | <img src="/results/synthetic/2_proposed.png" width="400">  |
| <img src="/results/synthetic/3_in.bmp" width="400">  | <img src="/results/synthetic/3_TILT.png" width="400">  | <img src="/results/synthetic/3_proposed.png" width="400">  |
| <img src="/results/synthetic/4_in.bmp" width="400">  | <img src="/results/synthetic/4_TILT.png" width="400">  | <img src="/results/synthetic/4_proposed.png" width="400">  |
| <img src="/results/synthetic/5_in.bmp" width="400">  | <img src="/results/synthetic/5_TILT.png" width="400">  | <img src="/results/synthetic/5_proposed.png" width="400">  |
| <img src="/results/synthetic/6_in.bmp" width="400">  | <img src="/results/synthetic/6_TILT.png" width="400">  | <img src="/results/synthetic/6_proposed.png" width="400">  |
| <img src="/results/synthetic/7_in.bmp" width="400">  | <img src="/results/synthetic/7_TILT.png" width="400">  | <img src="/results/synthetic/7_proposed.png" width="400">  |
| <img src="/results/synthetic/8_in.bmp" width="400">  | <img src="/results/synthetic/8_TILT.png" width="400">  | <img src="/results/synthetic/8_proposed.png" width="400">  |
| <img src="/results/synthetic/9_in.bmp" width="400">  | <img src="/results/synthetic/9_TILT.png" width="400">  | <img src="/results/synthetic/9_proposed.png" width="400">  |
| <img src="/results/synthetic/10_in.bmp" width="400">  | <img src="/results/synthetic/10_TILT.png" width="400">  | <img src="/results/synthetic/10_proposed.png" width="400">  |

## Excutable program
comming soon...

## Reference
[1] Z Zhang, A Ganesh, X Liang and Y Ma, "TILT: Transform Invariant Low-Rank Textures", IJCV 2012.

[2] B Wang, C Liu and X Ding, "A Scheme for Automatic Text Rectification in Real Scene Images", SPIE/IS&T 2015.
