﻿
# Single Shot MultiBox Detector

This is a kind of Single-Stage Detector (SSD) which detects objects in
images using a single deep neural network.

<br/>

<p align="Center">
  <img src="https://raw.githubusercontent.com/wiki/CuriousLad1000/Computer-Vision_Image-Processing/images/db3d3a6a28bbe709278f51b2c2aadc71a5d0135b.png">
</p>

<br/>
<br/>

## What is this?

The code will either take a camera feed or a video feed and strip frames
from it to detect multiple objects within a single frame. It uses a
simple CNN model to train and provides information whether the object is
present within the anchor box or not by providing a score and fine-tune
the box. For more details check the file <i> keras_ssd7.py </i>
under models directory.

## How it works?

SSD is designed to run in real-time. This method speeds up the process
by getting rid of Region Proposal Network used in other methods like
<i> Faster R-CNN </i>. It uses small convolutional filters to
compute both location and class score of an object.

The detection mechanism works in two parts, one extracts feature maps
and other applies convolution filters to detect objects.

After extracting the feature maps, SSD applies 3x3 convolution filters
for each cell to make predictions. These filters compute results like
regular CNN filters. Each filter outputs (no. of classes + 4 extra (for
bounding boxes, coordinates and width, height) ). The default bounding
boxes are selected carefully to cover wide number of real-life objects
(4 to 6 boxes and 1 pred. per box). Also, the coordinates of returned
box are relative to the default boundary boxes at each cell (∆cx, ∆cy,
∆w, ∆h). <i>" the offsets (difference) to the default box at each cell
for its center (*cx*, *cy*), the width and the height. For each feature
map layers, it shares the same set of default boxes centered at the
corresponding cell. But different layers use different sets of default
boxes to customize object detections at different resolutions. The 4
green boxes below illustrate 4 default boundary boxes.\" </i>

> note: Higher resolution feature maps are responsible for detecting smaller objects.


<br/>

<p align="Center">
  <img src="https://raw.githubusercontent.com/wiki/CuriousLad1000/Computer-Vision_Image-Processing/images/d2e2a8ab976cd4e292967c102c2ded3e979865f6.png">
</p>

<br/>
<br/>


<br/>

<p align="Center">
  <img src="https://raw.githubusercontent.com/wiki/CuriousLad1000/Computer-Vision_Image-Processing/images/fab3738cfd641ebf639435c63c91ccf2cfd741fd.png">
</p>

<br/>
<br/>

For detailed explanation, check references.

reference1: [SSD object detection](https://jonathan-hui.medium.com/ssd-object-detection-single-shot-multibox-detector-for-real-time-processing-9bd8deac0e06)

reference2: [Understanding SSD MultiBox --- Real-Time Object Detection In Deep Learning](https://towardsdatascience.com/understanding-ssd-multibox-real-time-object-detection-in-deep-learning-495ef744fab)

## Snapshot


<br/>

<p align="Center">
  <img src="https://raw.githubusercontent.com/wiki/CuriousLad1000/Computer-Vision_Image-Processing/images/70f18bfefa46f46c02a81d4516570281cfdc2c9c.png">
</p>

<br/>
<br/>

