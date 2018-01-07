# Scene text rectification using glyph and character alignment properties


<p align="center">
<img src="/abs.png" width="700"> 
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
<img src="/iter1.png" height="120"> <img src="/iter2.png" height="120"> 
</p>

### Character segmentation

We extract character components using a projection profile method, and separate characters 
with the projection value of more than mean stroke with value.

<p align="center">
<img src="/seg1.png" height="80">
<img src="/seg2.png" height="120"> 
</p>

### Text rectification

Alignment of characters represents following two properties that are vertical and horizontal 
alignment properties. The vertical alignment means that characters in the undistorted text 
are aligned to the horizontal-straight lines, specifically the most top and bottom points of
characters are on one of two lines. The horizontal alignment means that the character widhts of 
undistorted text have minimal values. 
We perform text rectification by using two alignment properties.

<p align="center">
<img src="/vert_align.png" width="350">
<img src="/hori_align.png" width="380"> 
</p>
<p align="center">
vertical & horizontal alignment properties
</p>

<p align="center">
<img src="/recti.png" width="700">
</p>
<p align="center">
rectification using alignment properties
</p>

## Experimental results
### Scene text dataset
We evaluate our method on the scene text dataset [2], that is consisted of real and synthetic text images. 
They are binarized text images and include English and Chinese characters.
<p align="center">
<img src="/dataset.png" width="350">
</p>

### OCR accuracy
The performance is evaluated in terms of OCR accuracy, which is defined as
\begin{equation}
\mbox{accuracy}(R,G)=1-\dfrac{L(R,G)}{\max(\#R,\#G)},
\end{equation}
where $R$ is a recognition result string, $G$ is the ground truth string, $\#(\cdot)$ is the number of characters in the string, and $L(x,y)$ means the Levenshtein distance between two strings \citep{levenstein1965binary}. The distance is defined as the minimum number of character edits (insertion, deletion, and substitution) to transform one string to the other.

### Rectified text images

## Excutable program
## Reference
[1]
[2]
