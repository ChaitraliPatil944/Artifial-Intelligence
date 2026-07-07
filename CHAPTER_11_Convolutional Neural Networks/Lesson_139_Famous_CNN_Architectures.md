# Chapter 10 -- Convolutional Neural Networks (CNNs)

# Lesson 139 -- Famous CNN Architectures

> **Modern CNN architectures evolved by solving the limitations of
> earlier models. Each new architecture introduced an innovation that
> improved accuracy, training stability, computational efficiency, or
> scalability. Understanding this evolution is essential for interviews
> and real-world deep learning.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand the evolution of CNNs.
-   Learn the key innovations of major architectures.
-   Compare their strengths and weaknesses.
-   Know when each architecture is appropriate.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  Why CNN Architectures Evolved
2.  Timeline
3.  LeNet-5
4.  AlexNet
5.  ZFNet
6.  VGG
7.  GoogLeNet (Inception)
8.  ResNet
9.  DenseNet
10. MobileNet
11. EfficientNet
12. Comparison Table
13. TensorFlow Transfer Learning
14. Mini Project
15. Interview Questions
16. Summary
17. What's Next?

------------------------------------------------------------------------

# 1. Why CNN Architectures Evolved

Each generation solved a major problem:

``` text
Better Accuracy
      │
Faster Training
      │
Fewer Parameters
      │
Deeper Networks
      │
Mobile Deployment
```

------------------------------------------------------------------------

# 2. Timeline

``` text
1998  LeNet
   │
2012  AlexNet
   │
2013  ZFNet
   │
2014  VGG
   │
2014  GoogLeNet
   │
2015  ResNet
   │
2017  DenseNet
   │
2018  MobileNet
   │
2019  EfficientNet
```

------------------------------------------------------------------------

# 3. LeNet-5 (1998)

Purpose: - Handwritten digit recognition.

Innovation: - First successful CNN.

Pros: - Simple - Historic

Cons: - Small network - Limited capability

------------------------------------------------------------------------

# 4. AlexNet (2012)

Innovation: - ReLU - Dropout - GPU training - Data augmentation

Impact: - Won ImageNet 2012 and sparked the deep learning revolution.

------------------------------------------------------------------------

# 5. ZFNet

Improved AlexNet by:

-   Better visualization
-   Better hyperparameter choices
-   Improved feature understanding

------------------------------------------------------------------------

# 6. VGG

Idea:

Use many small 3×3 convolutions.

Pros:

-   Simple architecture
-   Excellent feature extraction

Cons:

-   Very large number of parameters
-   Slow

------------------------------------------------------------------------

# 7. GoogLeNet (Inception)

Innovation:

Inception modules process multiple filter sizes in parallel.

``` text
1×1
3×3
5×5
Pooling
   │
Concatenate
```

Pros:

-   High accuracy
-   Parameter efficient

------------------------------------------------------------------------

# 8. ResNet

Problem solved:

Deep networks suffered from vanishing gradients.

Solution:

Residual (skip) connections.

``` text
Input
 │
Conv
 │
+─────────+
│         │
└────────►+
          │
       Output
```

Allowed training of extremely deep networks.

------------------------------------------------------------------------

# 9. DenseNet

Every layer connects to every later layer.

Benefits:

-   Better gradient flow
-   Feature reuse
-   Fewer redundant features

------------------------------------------------------------------------

# 10. MobileNet

Designed for:

-   Smartphones
-   Embedded devices

Innovation:

Depthwise separable convolutions.

Benefits:

-   Small
-   Fast
-   Energy efficient

------------------------------------------------------------------------

# 11. EfficientNet

Key idea:

Scale three dimensions together:

-   Depth
-   Width
-   Resolution

Compound scaling achieves excellent accuracy with fewer parameters.

------------------------------------------------------------------------

# 12. Comparison Table

  Architecture   Main Innovation         Best Use
  -------------- ----------------------- ----------------------------
  LeNet          First CNN               Digits
  AlexNet        Deep CNN + ReLU         General vision
  ZFNet          Visualization           Research
  VGG            3×3 convolutions        Transfer learning
  GoogLeNet      Inception               Efficient vision
  ResNet         Skip connections        Very deep models
  DenseNet       Dense connections       Feature reuse
  MobileNet      Depthwise convolution   Mobile devices
  EfficientNet   Compound scaling        High accuracy & efficiency

------------------------------------------------------------------------

# 13. TensorFlow Transfer Learning

``` python
from tensorflow.keras.applications import ResNet50

model = ResNet50(
    weights="imagenet",
    include_top=False,
    input_shape=(224,224,3)
)
```

Other pretrained models:

-   VGG16
-   MobileNetV2
-   EfficientNetB0

------------------------------------------------------------------------

# 14. Mini Project

1.  Load a pretrained ResNet50.
2.  Replace the classifier.
3.  Fine-tune on a custom dataset.
4.  Compare with MobileNetV2.
5.  Measure accuracy and inference speed.

------------------------------------------------------------------------

# 15. Interview Questions

### Which architecture introduced skip connections?

ResNet.

### Why is MobileNet suitable for phones?

It uses depthwise separable convolutions, reducing computation.

### Which model popularized deep learning for computer vision?

AlexNet.

### What is EfficientNet's main contribution?

Compound scaling of depth, width, and resolution.

------------------------------------------------------------------------

# 16. Summary

You learned:

-   Evolution of CNNs.
-   Major CNN architectures.
-   Innovations introduced by each model.
-   Comparison and use cases.
-   TensorFlow transfer learning.

------------------------------------------------------------------------

# 17. What's Next?

**Lesson 140 -- Transfer Learning & Fine-Tuning**

You'll learn how to reuse pretrained CNNs, freeze and unfreeze layers,
fine-tune models for new datasets, and dramatically reduce training time
while achieving state-of-the-art performance.
