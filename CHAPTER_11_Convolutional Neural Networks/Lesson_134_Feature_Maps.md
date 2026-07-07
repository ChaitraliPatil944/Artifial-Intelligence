# Chapter 10 -- Convolutional Neural Networks (CNNs)

# Lesson 134 -- Feature Maps

> **A Feature Map is the output produced after applying a convolution
> filter to an input image or a previous feature map. Each feature map
> highlights a specific visual pattern, allowing CNNs to gradually
> transform raw pixels into meaningful representations such as edges,
> textures, shapes, and objects.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what Feature Maps are.
-   Learn how kernels create feature maps.
-   Understand multiple feature maps.
-   Learn how feature maps evolve through CNN layers.
-   Study feature map dimensions.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is a Feature Map?
2.  How Feature Maps are Created
3.  One Filter vs Multiple Filters
4.  Feature Map Dimensions
5.  Evolution Through CNN Layers
6.  Feature Maps vs Activation Maps
7.  Visualizing Feature Maps
8.  Python Implementation
9.  Mini Project
10. Interview Questions
11. Summary
12. What's Next?

------------------------------------------------------------------------

# 1. What is a Feature Map?

A feature map is the result of applying a convolution filter.

``` text
Input Image
     │
 Convolution
     │
 Feature Map
```

Each feature map represents one learned visual feature.

------------------------------------------------------------------------

# 2. How Feature Maps are Created

``` text
Image
   │
3×3 Kernel
   │
Convolution
   │
Feature Map
```

Every value in the feature map is computed by:

1.  Sliding the kernel.
2.  Multiplying corresponding values.
3.  Summing the products.
4.  Storing the result.

------------------------------------------------------------------------

# 3. One Filter vs Multiple Filters

### One Filter

``` text
Image
  │
Filter
  │
One Feature Map
```

### Multiple Filters

``` text
Image
 │
 ├── Filter 1 → Feature Map 1
 ├── Filter 2 → Feature Map 2
 ├── Filter 3 → Feature Map 3
 └── Filter N → Feature Map N
```

If a convolution layer has **64 filters**, it produces **64 feature
maps**.

------------------------------------------------------------------------

# 4. Feature Map Dimensions

Output height and width:

``` text
Output = ((N - F + 2P) / S) + 1
```

Where:

-   **N** = Input size
-   **F** = Filter size
-   **P** = Padding
-   **S** = Stride

Example:

``` text
Input = 32×32
Kernel = 3×3
Padding = 1
Stride = 1

Output = 32×32
```

Output depth equals the **number of filters**.

------------------------------------------------------------------------

# 5. Evolution Through CNN Layers

``` text
Input Image
      │
Layer 1
Edges
      │
Layer 2
Corners & Textures
      │
Layer 3
Parts of Objects
      │
Deep Layers
Whole Objects
```

Early layers learn simple patterns.

Deep layers combine them into complex concepts.

------------------------------------------------------------------------

# 6. Feature Maps vs Activation Maps

  -----------------------------------------------------------------------
  Feature Map                     Activation Map
  ------------------------------- ---------------------------------------
  Output of convolution           Usually feature map after activation
                                  (e.g., ReLU)

  Raw filter response             Non-linearly transformed response
  -----------------------------------------------------------------------

In many practical discussions, the terms are used interchangeably,
though technically they differ.

------------------------------------------------------------------------

# 7. Visualizing Feature Maps

Visualization helps us understand what a CNN has learned.

Example:

``` text
Original Image

↓

Edge Feature Map

↓

Texture Feature Map

↓

Shape Feature Map
```

Bright regions indicate strong responses from a filter.

------------------------------------------------------------------------

# 8. Python Implementation

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Conv2D

model = Sequential([
    Conv2D(
        filters=32,
        kernel_size=(3,3),
        activation="relu",
        input_shape=(224,224,3)
    )
])

model.summary()
```

The output tensor contains 32 feature maps.

------------------------------------------------------------------------

# 9. Mini Project

1.  Train a simple CNN.
2.  Select an input image.
3.  Extract the output of the first convolution layer.
4.  Display all feature maps.
5.  Compare early and deeper layer feature maps.

------------------------------------------------------------------------

# 10. Interview Questions

### What is a feature map?

The output produced after applying a convolution filter.

### How many feature maps does a convolution layer produce?

One feature map per filter.

### What do early feature maps detect?

Edges, corners, and simple textures.

### Why are feature maps important?

They transform raw pixels into increasingly meaningful visual
representations.

------------------------------------------------------------------------

# 11. Summary

You learned:

-   Feature map fundamentals.
-   Relationship between filters and feature maps.
-   Output dimensions.
-   Evolution through CNN layers.
-   Visualization techniques.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 12. What's Next?

**Lesson 135 -- Padding**

You'll learn why padding is necessary, understand valid and same
padding, calculate output dimensions, prevent information loss at image
borders, and see how padding affects convolution results.
