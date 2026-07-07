# Chapter 10 -- Convolutional Neural Networks (CNNs)

# Lesson 141 -- Image Augmentation

> **Image Augmentation is the process of creating new training images by
> applying realistic transformations to existing images. It artificially
> increases the diversity of a dataset, helping deep learning models
> generalize better, reduce overfitting, and perform well on unseen
> data.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Image Augmentation.
-   Learn why augmentation is important.
-   Study common augmentation techniques.
-   Differentiate online and offline augmentation.
-   Learn best practices.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Image Augmentation?
2.  Why Image Augmentation?
3.  Common Augmentation Techniques
4.  Online vs Offline Augmentation
5.  Choosing the Right Augmentations
6.  Advantages & Limitations
7.  TensorFlow Implementation
8.  Albumentations Overview
9.  Mini Project
10. Interview Questions
11. Summary
12. What's Next?

------------------------------------------------------------------------

# 1. What is Image Augmentation?

Instead of collecting thousands of new images, we generate realistic
variations of existing ones.

``` text
Original Image
      │
Augmentation
      │
Many New Images
```

The object's identity remains the same even though its appearance
changes.

------------------------------------------------------------------------

# 2. Why Image Augmentation?

Benefits:

-   Increases effective dataset size.
-   Reduces overfitting.
-   Improves generalization.
-   Makes models robust to real-world variations.

Example:

``` text
Original Cat

↓

Rotated Cat

↓

Zoomed Cat

↓

Brighter Cat

↓

Still a Cat
```

------------------------------------------------------------------------

# 3. Common Augmentation Techniques

### Rotation

Rotate the image by a small angle.

``` text
↻ 15°
```

Useful when object orientation varies.

------------------------------------------------------------------------

### Horizontal Flip

``` text
←→
```

Common for natural images.

------------------------------------------------------------------------

### Vertical Flip

Less common.

Avoid for datasets where orientation matters (e.g., handwritten digits).

------------------------------------------------------------------------

### Translation

Move the image horizontally or vertically.

``` text
⬅ ➡ ⬆ ⬇
```

Improves translation robustness.

------------------------------------------------------------------------

### Zoom

Zoom in or out while preserving the object.

------------------------------------------------------------------------

### Cropping

Randomly crop part of the image.

Encourages the model to recognize partial objects.

------------------------------------------------------------------------

### Brightness & Contrast

Adjust lighting conditions.

Useful for real-world photographs.

------------------------------------------------------------------------

### Noise Injection

Add random noise.

Improves robustness to noisy sensors.

------------------------------------------------------------------------

### Cutout / Random Erasing

Randomly remove a patch of the image.

Helps prevent over-reliance on one region.

------------------------------------------------------------------------

### MixUp (Overview)

Creates a new sample by blending two images and their labels.

------------------------------------------------------------------------

### CutMix (Overview)

Copies a patch from one image into another and mixes the labels
accordingly.

------------------------------------------------------------------------

# 4. Online vs Offline Augmentation

  -----------------------------------------------------------------------
  Offline                                 Online
  --------------------------------------- -------------------------------
  Images are augmented before training    Images are augmented during
  and saved                               training

  Larger storage                          Minimal storage

  Fixed augmented dataset                 Infinite random variations
  -----------------------------------------------------------------------

Online augmentation is the standard approach in modern deep learning.

------------------------------------------------------------------------

# 5. Choosing the Right Augmentations

  Dataset            Recommended Augmentations
  ------------------ -----------------------------------------
  Animals            Flip, Rotation, Zoom
  Medical Images     Small rotations, brightness adjustments
  OCR                Slight rotation, translation
  Faces              Brightness, crop, slight rotation
  Satellite Images   Rotation, flip

Avoid unrealistic transformations that change the class label.

------------------------------------------------------------------------

# 6. Advantages & Limitations

## Advantages

-   Better generalization.
-   Reduces overfitting.
-   Improves robustness.
-   Requires no new data collection.

## Limitations

-   Unrealistic augmentations can hurt performance.
-   Adds computation during training.
-   Not a substitute for diverse, high-quality data.

------------------------------------------------------------------------

# 7. TensorFlow Implementation

``` python
from tensorflow.keras import Sequential
from tensorflow.keras.layers import (
    RandomFlip,
    RandomRotation,
    RandomZoom
)

augmentation = Sequential([
    RandomFlip("horizontal"),
    RandomRotation(0.1),
    RandomZoom(0.2)
])
```

------------------------------------------------------------------------

# 8. Albumentations Overview

Albumentations is a popular Python library for fast and flexible image
augmentation.

Example capabilities:

-   Rotation
-   Blur
-   Noise
-   Perspective transforms
-   Elastic deformation
-   Color adjustments

It is widely used in computer vision competitions and production
pipelines.

------------------------------------------------------------------------

# 9. Mini Project

1.  Load an image dataset.
2.  Apply RandomFlip.
3.  Apply RandomRotation.
4.  Train a CNN with augmentation.
5.  Compare results with training without augmentation.

------------------------------------------------------------------------

# 10. Interview Questions

### What is Image Augmentation?

A technique that generates transformed versions of existing images to
improve model generalization.

### Why is augmentation useful?

It increases data diversity and reduces overfitting.

### Difference between online and offline augmentation?

Offline augmentation creates and stores transformed images beforehand,
while online augmentation generates them during training.

### Can augmentation replace collecting more data?

No. It complements real data but cannot replace genuine diversity.

------------------------------------------------------------------------

# 11. Summary

You learned:

-   Image Augmentation fundamentals.
-   Common augmentation techniques.
-   Online vs offline augmentation.
-   Best practices.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 12. What's Next?

**Lesson 142 -- CNN Training Pipeline**

You'll learn the complete workflow for training CNNs, including dataset
preparation, preprocessing, augmentation, model compilation, training,
validation, evaluation, checkpointing, and deployment-ready practices.
