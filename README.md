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



## Excutable program
comming soon...

## Reference
[1] Z Zhang, A Ganesh, X Liang and Y Ma, "TILT: Transform Invariant Low-Rank Textures", IJCV 2012.
[2] B Wang, C Liu and X Ding, "A Scheme for Automatic Text Rectification in Real Scene Images", SPIE/IS&T 2015.
