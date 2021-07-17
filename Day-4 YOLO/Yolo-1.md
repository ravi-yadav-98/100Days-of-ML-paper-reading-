## You Only Look Once: Unified, Real-Time Object Detection
- [paper link](https://arxiv.org/abs/1506.02640)

### Introduction
- we frame object detection as a regression problem to spatially separated bounding boxes and
associated class probabilities
- process images 45 frames per second
- It outperforms all other detection methods, including DPM and RCNN, by a wide margin.
- mAP - mean average precision
- Current detection systems repurpose classifiers to perform detection
- these systems take a  classifier for that object and evaluate it at various locations
and scales in a test image
- Example: Systems like deformable parts
models (DPM) use a sliding window approach where the
classifier is run at evenly spaced locations over the entire
image 
- More recent approaches like R-CNN use region proposal
methods to first generate potential bounding boxes in an image and then run a classifier on these proposed boxes
- These methods are complex, slow and hard to optimize

### YOLO: 
-  It reframes object detection as a single regression problem, straight from image pixels to bounding box coordinates and class probabilities
-   Using our system, you only
look once (YOLO) at an image to predict what objects are
present and where they are.
- YOLO trains on full images and directly optimizes detection performance
- YOLO is fast and simple.
- YOLO achieves more than twice the mean average precision of other real-time systems
-  YOLO makes less than half the number of
background errors compared to Fast R-CNN.
- 
