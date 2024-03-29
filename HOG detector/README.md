﻿
# HOG descriptor to detect people in a motion picture (a gif)

Histogram Oriented Gradients is a feature descriptor used for object
detection in an image. This technique focuses on the shape of the
object. HOG can also provide information about the direction of the edge
by fetching gradient and orientation of edges from the test image.

HOG counts the occurrences of the gradient orientation in localized
regions of the image.

## What is this?

This code uses HOG technique to detect the persons in the sample gif
image.

The task was to find the HOG detector parameters which are able to
detect both runners perfectly when they are fully visible (The first few
frames).

## How it works?

-   HOG takes an image of size (64x128) and is split into 8x8 cells

-   Gradient of image is calculated, that is the small changes in x and
    y directions are calculated by subtracting pixel values. The
    magnitude will be higher when an edge is detected due to sharp
    change in intensity.

-   Calculate the Magnitude and Orientation **Mag = sqrt((Grad_x)\^2 +
    (Grad_y)\^2 ))** and **Orient_theta = atan (Gy/Gx))**

-   Calculate Histogram of Gradients in 8x8 cells over 9 orientation
    bins.

-   Now, Normalize gradients to next level, 16x16 cell. This is done
    because the gradients are very sensitive to lighting changes and
    some parts of image might be brighter than others. To mitigate this,
    we normalize it. Now, since we are using four 9-bins, combining them
    would give us a bin of 36 and to normalize it,

K = sqrt((binVal_1)\^2+(binVal_2)\^2+ .......+(binVal_36)\^2)

Normalized vector = \[ binVal_1/K , binVal_2/K, ....., binVal_36/K\]

-   Now, get features for whole image, Feature dimensions = 7x15 (for
    overlapped tiling with 2x2 blocks) X 36 { 9 (orientations) X 4(2x2
    blocks) due to normalization } = 3780 features.

> <i> For detailed explanation refer to : [Link](https://www.analyticsvidhya.com/blog/2019/09/feature-engineering-images-introduction-hog-feature-descriptor/) </i>

<br/>

<p align="Center">
  <img src="https://raw.githubusercontent.com/wiki/CuriousLad1000/Computer-Vision_Image-Processing/images/c4ef9b73872f5f8d0a194b03a761fde1761a210b.png">
</p>

<br/>
<br/>

