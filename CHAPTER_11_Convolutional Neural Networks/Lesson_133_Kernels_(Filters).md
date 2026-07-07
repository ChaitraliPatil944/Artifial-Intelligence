# Chapter 10 -- Convolutional Neural Networks (CNNs)

# Lesson 133 -- Kernels (Filters)

> **A kernel (or filter) is a small matrix that slides across an image
> during convolution to detect specific visual patterns. Different
> kernels detect different features such as edges, corners, textures,
> blur, and sharpening. In CNNs, these filters are not manually designed
> but learned automatically from data.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what kernels are.
-   Learn why filters are needed.
-   Study handcrafted and learnable filters.
-   Learn common image processing kernels.
-   Understand how CNNs learn filters automatically.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is a Kernel?
2.  Why Kernels?
3.  Handcrafted vs Learnable Filters
4.  Common Kernels
5.  Edge Detection
6.  CNN Learnable Filters
7.  Multiple Filters
8.  Feature Hierarchy
9.  Python Examples
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is a Kernel?

A kernel is a **small matrix** that scans an image.

``` text
Image
  │
Kernel
  │
Convolution
  │
Feature Map
```

Typical sizes:

-   3×3
-   5×5
-   7×7

Smaller kernels are computationally efficient.

------------------------------------------------------------------------

# 2. Why Kernels?

Different kernels detect different patterns.

``` text
Image

↓

Edge Filter

↓

Edges
```

Without filters, CNNs would not learn meaningful visual features.

------------------------------------------------------------------------

# 3. Handcrafted vs Learnable Filters

  Handcrafted Filters   Learnable Filters
  --------------------- ----------------------------
  Designed by humans    Learned during training
  Fixed values          Updated by backpropagation
  Traditional CV        Modern CNNs

Modern CNNs rarely use handcrafted filters inside the network.

------------------------------------------------------------------------

# 4. Common Kernels

### Identity

``` text
0 0 0
0 1 0
0 0 0
```

Leaves the image unchanged.

### Blur

``` text
1 1 1
1 1 1
1 1 1
```

(Usually normalized by dividing by 9.)

Reduces image noise.

### Sharpen

``` text
 0 -1  0
-1  5 -1
 0 -1  0
```

Enhances edges and details.

------------------------------------------------------------------------

# 5. Edge Detection

### Vertical Edge (Sobel)

``` text
-1 0 1
-2 0 2
-1 0 1
```

### Horizontal Edge (Sobel)

``` text
-1 -2 -1
 0  0  0
 1  2  1
```

Other popular filters:

-   Prewitt
-   Laplacian

Each highlights different image structures.

------------------------------------------------------------------------

# 6. CNN Learnable Filters

Instead of fixed kernels:

``` text
Random Filter

↓

Training

↓

Useful Filter
```

During training:

-   Random initialization
-   Forward propagation
-   Backpropagation
-   Weight updates

Eventually the filter specializes in detecting useful patterns.

------------------------------------------------------------------------

# 7. Multiple Filters

A CNN layer contains many filters.

``` text
Image
 │
 ├── Filter 1 → Edges
 ├── Filter 2 → Corners
 ├── Filter 3 → Texture
 ├── Filter 4 → Curves
 └── Filter N → Complex Patterns

↓

Many Feature Maps
```

Each filter extracts different information.

------------------------------------------------------------------------

# 8. Feature Hierarchy

``` text
Layer 1

Edges

↓

Layer 2

Corners & Textures

↓

Layer 3

Eyes / Wheels

↓

Deep Layers

Faces / Cars / Animals
```

CNNs gradually build complex understanding from simple patterns.

------------------------------------------------------------------------

# 9. Python Examples

OpenCV:

``` python
import cv2
import numpy as np

kernel = np.array([
    [-1,0,1],
    [-2,0,2],
    [-1,0,1]
])

edges = cv2.filter2D(image, -1, kernel)
```

TensorFlow:

``` python
from tensorflow.keras.layers import Conv2D

Conv2D(
    filters=32,
    kernel_size=(3,3),
    activation="relu"
)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Load a grayscale image.
2.  Apply blur, sharpen, and Sobel filters.
3.  Compare outputs.
4.  Build a simple CNN.
5.  Visualize the learned filters after training.

------------------------------------------------------------------------

# 11. Interview Questions

### What is a kernel?

A small matrix used during convolution to detect visual patterns.

### Difference between handcrafted and learnable filters?

Handcrafted filters are manually designed, while CNN filters are learned
automatically.

### Why do CNNs use multiple filters?

To detect many different features simultaneously.

### What do early CNN layers usually learn?

Edges, corners, and simple textures.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Kernels and filters.
-   Common handcrafted kernels.
-   Learnable CNN filters.
-   Multiple feature maps.
-   Feature hierarchy.
-   OpenCV and TensorFlow examples.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 134 -- Feature Maps**

You'll learn how convolution outputs become feature maps, how multiple
filters generate multiple channels, how feature maps evolve through deep
CNNs, and why they are essential for image understanding.
