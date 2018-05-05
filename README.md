# CS766_CV_Project
This project is aimed at enabling automatic content summarization of videos by creating a representative mosaic of the video's object of focus. We intend to do this in a three-step process involving real time object detection, salient object identification and image mosaicing. Each of these steps is described in detail in the forthcoming section.

Read more about YOLO (in darknet) [Real-time object detection and classification. Paper: [version 1](https://arxiv.org/pdf/1506.02640.pdf), [version 2](https://arxiv.org/pdf/1612.08242.pdf)] and download weight files [here](http://pjreddie.com/darknet/yolo/). Save this downloaded weight file as yolov2.weights in bin folder.

## Dependencies

Python3, tensorflow, numpy, PIL, opencv 3.

# Methodology
Our proposed content summarization pipeline comprises of three modules namely Object detection, Salient Object Identification and Image Mosaicing.

1 Object Detection
Object detection is the problem of finding and classifying a variable number of objects on an image. Object detection has proven to be a hard problem as compared to classification, since its output is variable in dimensions due to the inherent differences in object size and number across images. Object detection in videos is an even more challenging task than object detection in images primarily due to the motion and blur effects that result in detection failures on certain frames.

A traditional method for object detection is using Histogram of Oriented Gradients(HOG) features and Support Vector Machine (SVM) for classification. It requires a multi-scale sliding window making it much slower. In recent years deep learning has been a real game changer in computer vision. Deep learning models have virtually replaced classical techniques for the tasks of image classification and object detection and are currently an active area of research in computer vision. Many deep learning models are already in place that are state of the art in object detection. These models are fast and provide high accuracy and detection efficiency. In this phase, we leveraged state-of-the-art frameworks like R-CNN, R-FCN, YOLO and SSD for application-specific object detection.

2 Salient Object Identification
After obtaining the output of the object detection module, we extracted information about the content and salient objects of the video based on a mixture of heuristics and learned decisions. In this phase, we determined the content of the video by analyzing identified object categories, their frequency of occurrence and the mutual relationship between objects detected in the video. The output of this module was a list of tags or categories associated with identified objects along with their frames of occurrence in the video as well as the object of interest (the salient object).

3 Image Mosaicing
Mosaicing is an old art technique where pictures or designs are formed by inlaying small bits of colored stone, glass, or tile. These small bits are visible close up, but the boundaries of the bits will blend and a single recognizable image will show at a distance. In the modern digital world, this ancient art form has been transformed and combined with new technologies. Instead of using pure-colored blocks, entire images can be used as tiles to make an overall pictures.

After obtaining the output of the Object Detection and Salient Object Identification modules, we chose a representative image as our target image. Using other occurrences of the same object (as well as other significant objects), we reconstructed the target image in the form of a mosaic. This aesthetic visualization would be our final output that succinctly provides a visual preview of the video content and an overview of the object of interest.
