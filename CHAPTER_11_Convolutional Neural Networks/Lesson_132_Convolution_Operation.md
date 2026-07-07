# Chapter 10 -- Convolutional Neural Networks (CNNs)

# Lesson 132 -- Convolution Operation

> **Convolution is the core mathematical operation behind Convolutional
> Neural Networks. Instead of connecting every pixel to every neuron,
> convolution scans an image with a small filter, extracting meaningful
> patterns such as edges, corners, textures, and shapes while using far
> fewer parameters than a fully connected network.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what convolution is.
-   Learn why convolution was invented.
-   Understand filters and sliding windows.
-   Perform convolution step by step.
-   Calculate output dimensions.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Convolution?
2.  Why Convolution?
3.  Filters (Kernels)
4.  Sliding Window
5.  Step-by-Step Numerical Example
6.  Feature Maps
7.  Output Size Formula
8.  Multiple Filters
9.  Why Convolution is Powerful
10. Python Implementation
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is Convolution?

Convolution applies a small matrix (**kernel/filter**) over an image.

``` text
Image
   │
Kernel
   │
Multiply
   │
Sum
   │
Feature Map
```

Instead of analyzing the entire image at once, the network examines
small local regions.

------------------------------------------------------------------------

# 2. Why Convolution?

Dense networks:

-   Require millions of parameters.
-   Ignore spatial relationships.

Convolution:

-   Preserves locality.
-   Shares weights.
-   Greatly reduces parameters.
-   Learns visual features automatically.

------------------------------------------------------------------------

# 3. Filters (Kernels)

Example 3×3 kernel:

``` text
1  0 -1
1  0 -1
1  0 -1
```

A kernel is a small matrix that detects specific patterns such as
vertical edges.

------------------------------------------------------------------------

# 4. Sliding Window

The kernel moves across the image one step at a time.

``` text
Image

□□□□□
□■■■□
□■■■□
□■■■□
□□□□□

↓

Move Right

↓

Move Down
```

At every position:

1.  Multiply corresponding values.
2.  Add them.
3.  Store the result.

------------------------------------------------------------------------

# 5. Step-by-Step Numerical Example

Input:

``` text
1 2 3
4 5 6
7 8 9
```

Kernel:

``` text
1 0
0 1
```

Calculation on the first window:

``` text
(1×1)

+

(2×0)

+

(4×0)

+

(5×1)

=

6
```

The value **6** becomes the first element of the output feature map.

------------------------------------------------------------------------

# 6. Feature Maps

After scanning the image:

``` text
Input Image

↓

Convolution

↓

Feature Map
```

Different filters create different feature maps.

Examples:

-   Edge map
-   Texture map
-   Corner map

------------------------------------------------------------------------

# 7. Output Size Formula

Without padding:

``` text
Output

=

(Input − Kernel)

/

Stride

+

1
```

Mathematically:

``` text
Output = ((N - F) / S) + 1
```

Where:

-   **N** = Input size
-   **F** = Filter size
-   **S** = Stride

Example:

``` text
Input = 5

Kernel = 3

Stride = 1

Output = ((5-3)/1)+1 = 3
```

------------------------------------------------------------------------

# 8. Multiple Filters

One image can be processed by many filters.

``` text
Image
 │
 ├── Edge Filter
 ├── Corner Filter
 ├── Texture Filter
 └── Shape Filter

↓

Multiple Feature Maps
```

Each filter learns a different visual pattern.

------------------------------------------------------------------------

# 9. Why Convolution is Powerful

Advantages:

-   Local feature extraction.
-   Weight sharing.
-   Translation awareness.
-   Fewer parameters.
-   Better generalization.

This makes CNNs highly effective for image analysis.

------------------------------------------------------------------------

# 10. Python Implementation

``` python
import tensorflow as tf

layer = tf.keras.layers.Conv2D(
    filters=32,
    kernel_size=(3,3),
    strides=1,
    padding="valid",
    activation="relu"
)
```

NumPy example:

``` python
import numpy as np

image = np.array([[1,2,3],
                  [4,5,6],
                  [7,8,9]])

kernel = np.array([[1,0],
                   [0,1]])
```

------------------------------------------------------------------------

# 11. Mini Project

1.  Create a small grayscale image matrix.
2.  Define a 3×3 kernel.
3.  Perform convolution manually.
4.  Verify the result with NumPy or TensorFlow.
5.  Visualize the feature map.

------------------------------------------------------------------------

# 12. Interview Questions

### What is convolution?

A mathematical operation that extracts local features by sliding a
kernel across an image.

### What is a kernel?

A small matrix used to detect patterns.

### Why is convolution better than dense layers for images?

It preserves spatial information while drastically reducing parameters.

### What is a feature map?

The output produced after applying a convolution filter.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   Convolution fundamentals.
-   Kernels.
-   Sliding windows.
-   Feature maps.
-   Output size calculation.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 133 -- Kernels (Filters)**

You'll learn how different kernels detect edges, textures, and shapes,
understand learnable filters, common handcrafted kernels (Sobel,
Prewitt, Laplacian), and discover how CNNs automatically learn powerful
visual detectors during training.
