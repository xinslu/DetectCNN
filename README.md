# DetectCNN (Pronounced Detection)

First off stupid pun, I know. This is an OCaml Implementation of the Mask Region Based Convolutional Neural Network or Mask R-CNN Paper (https://arxiv.org/pdf/1703.06870.pdf), using owl. This document will also detail my understanding to concepts useful for this project.

# Instance Segmentation

Instance segmentation is the image recognition task that deals with using machine learning to distinctly detect the presence of objects and demarcate them correctly.

# Semantic Segmentation

Semantic Segmentation s the image recognition task that deals with classifying each pixel into a fixed set of categories without differentiating object instance.

# R-CNN

Mask R-CNN is an improvement over Faster R-CNN but to understand that we must first go even deeper to Fast R-CNN. I will begin to understand what goes into this model using the research paper (https://arxiv.org/pdf/1311.2524.pdf).

An R-CNN can be broken down into 3 regions:
1. Category-independent region proposals, these define the different candidates for the detector.
2. CNN to extract a fixed length feature vector from the Region.
3. Class Specific linear SVMs.

## Region Proposal

Technically, R-CNN can be used with any type of semantic segmentation, but the research paper uses Selective Search so I'll be talking about that.

### Grouping in Selective Search

Grouping works by first making a rough segment of many different regions and continuously grouping them together. This is done by using Efficient Graph Based Segmentation and then using a greedy algorithm to iteratively group regions together: First the similarities between all neighboring regions are calculated. The two most similar regions are grouped together, and new similarities are calculated between the resulting region and its neighbors.

### Diversifying in Selective Search

Diversifying in Selection Sort works in 3 different ways:

1.  Varying the Color Spaces
2.  Complementary Similarity Measures
3.  Varying the starting regions.
