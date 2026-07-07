# Chapter 10 -- Convolutional Neural Networks (CNNs)

# Lesson 137 -- Pooling Layers

> **Pooling is a downsampling operation used in CNNs to reduce the
> spatial dimensions of feature maps while retaining the most important
> information. It decreases computation, reduces overfitting, and makes
> CNNs more robust to small translations in images.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what pooling is.
-   Learn why pooling is needed.
-   Compare Max Pooling, Average Pooling, and Global Average Pooling.
-   Understand pooling size and stride.
-   Learn translation invariance.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Pooling?
2.  Why Pooling?
3.  Max Pooling
4.  Average Pooling
5.  Global Average Pooling
6.  Pool Size and Stride
7.  Pooling vs Convolution
8.  Advantages & Limitations
9.  Python Implementation
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is Pooling?

Pooling reduces the size of a feature map.

``` text
Feature Map
     │
 Pooling
     │
Smaller Feature Map
```

Unlike convolution, pooling has **no learnable parameters**.

------------------------------------------------------------------------

# 2. Why Pooling?

Without pooling:

-   Large feature maps
-   High computation
-   More memory usage
-   Higher risk of overfitting

Pooling helps CNNs become faster and more efficient.

------------------------------------------------------------------------

# 3. Max Pooling

Max Pooling keeps the **largest value** in each region.

Example:

Input:

``` text
1 3
2 4
```

2×2 Max Pooling:

``` text
4
```

It preserves the strongest activation.

------------------------------------------------------------------------

# 4. Average Pooling

Average Pooling computes the mean value.

Input:

``` text
1 3
2 4
```

Output:

``` text
(1+3+2+4)/4 = 2.5
```

Useful when overall information is more important than the strongest
response.

------------------------------------------------------------------------

# 5. Global Average Pooling

Instead of producing another feature map, Global Average Pooling
computes **one average value per feature map**.

``` text
Feature Map

↓

Average

↓

Single Value
```

Widely used in modern CNNs to reduce parameters before the output layer.

------------------------------------------------------------------------

# 6. Pool Size and Stride

Typical configuration:

``` text
Pool Size = 2×2

Stride = 2
```

This halves the height and width.

Example:

``` text
Input: 32×32

↓

Pooling

↓

16×16
```

------------------------------------------------------------------------

# 7. Pooling vs Convolution

  Convolution             Pooling
  ----------------------- -------------------------------
  Learns features         Compresses features
  Has trainable filters   No trainable parameters
  Detects patterns        Reduces dimensions
  Produces feature maps   Produces smaller feature maps

------------------------------------------------------------------------

# 8. Advantages & Limitations

## Advantages

-   Reduces computation.
-   Reduces memory usage.
-   Helps prevent overfitting.
-   Improves translation robustness.

## Limitations

-   Loses some information.
-   Excessive pooling may remove important details.
-   Some modern architectures reduce pooling in favor of strided
    convolutions.

------------------------------------------------------------------------

# 9. Python Implementation

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Conv2D, MaxPooling2D

model = Sequential([
    Conv2D(32, (3,3), activation="relu", input_shape=(224,224,3)),
    MaxPooling2D(pool_size=(2,2), strides=2)
])
```

Average Pooling:

``` python
from tensorflow.keras.layers import AveragePooling2D

AveragePooling2D(pool_size=(2,2))
```

Global Average Pooling:

``` python
from tensorflow.keras.layers import GlobalAveragePooling2D

GlobalAveragePooling2D()
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Create a CNN with Max Pooling.
2.  Replace Max Pooling with Average Pooling.
3.  Compare feature map sizes.
4.  Measure training time.
5.  Compare validation accuracy.

------------------------------------------------------------------------

# 11. Interview Questions

### What is pooling?

A downsampling operation that reduces feature map dimensions.

### Difference between Max and Average Pooling?

Max Pooling keeps the highest value, while Average Pooling computes the
mean.

### Does pooling have trainable parameters?

No.

### Why is Global Average Pooling popular?

It greatly reduces parameters before the classifier and helps reduce
overfitting.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Pooling fundamentals.
-   Max, Average, and Global Average Pooling.
-   Pool size and stride.
-   Pooling vs convolution.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 138 -- CNN Architecture**

You'll learn how convolution, activation, pooling, and fully connected
layers are combined into complete CNN architectures, understand the
end-to-end image classification pipeline, and build your first complete
convolutional neural network.
