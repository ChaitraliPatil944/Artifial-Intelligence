# Chapter 10 -- Convolutional Neural Networks (CNNs)

# Lesson 135 -- Padding

> **Padding is the process of adding extra pixels around the border of
> an image before performing convolution. It prevents excessive
> shrinking of feature maps, preserves edge information, and gives
> convolution filters equal opportunities to learn from pixels at the
> center and the boundaries of an image.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what Padding is.
-   Learn why Padding is necessary.
-   Differentiate between Valid and Same Padding.
-   Learn Zero, Reflection, and Replication Padding.
-   Calculate output dimensions with padding.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Padding?
2.  Why Padding is Needed
3.  Types of Padding
4.  Zero Padding
5.  Reflection & Replication Padding
6.  Output Size Formula
7.  Padding Example
8.  Advantages
9.  Python Implementation
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is Padding?

Padding adds extra pixels around an image before convolution.

``` text
Original Image

□□□□□

↓

Padding

□□□□□□□
□□□□□□□
□□□□□□□
□□□□□□□
□□□□□□□
```

Most commonly, the added pixels are zeros.

------------------------------------------------------------------------

# 2. Why Padding is Needed

Without padding:

-   Output feature maps shrink after every convolution.
-   Border pixels participate in fewer convolution operations.
-   Information near image edges is gradually lost.

Example:

``` text
Input = 5×5

Kernel = 3×3

Padding = 0

↓

Output = 3×3
```

After several layers, the image becomes very small.

------------------------------------------------------------------------

# 3. Types of Padding

### Valid Padding

``` text
Padding = 0
```

-   No extra pixels added.
-   Output becomes smaller.

### Same Padding

Adds enough padding so that:

``` text
Output Size

=

Input Size
```

when stride = 1.

------------------------------------------------------------------------

# 4. Zero Padding

Most common padding technique.

Example:

``` text
Original

1 2
3 4
```

After padding:

``` text
0 0 0 0
0 1 2 0
0 3 4 0
0 0 0 0
```

Advantages:

-   Simple
-   Efficient
-   Widely supported

------------------------------------------------------------------------

# 5. Reflection & Replication Padding

### Reflection Padding

Border values are mirrored.

``` text
1 2

↓

2 1 2
1 2 1
2 1 2
```

### Replication Padding

Border pixels are copied.

``` text
1 2

↓

1 1 2
1 1 2
3 3 4
```

These methods can reduce artificial edge effects in some applications.

------------------------------------------------------------------------

# 6. Output Size Formula

General formula:

``` text
Output

=

((N - F + 2P) / S)

+

1
```

Where:

-   **N** = Input size
-   **F** = Filter size
-   **P** = Padding
-   **S** = Stride

Example:

``` text
Input = 32

Kernel = 3

Padding = 1

Stride = 1

Output

=

((32-3+2)/1)+1

=

32
```

Padding preserves the spatial dimensions.

------------------------------------------------------------------------

# 7. Padding Example

Without padding:

``` text
5×5

↓

3×3

↓

1×1

↓

Image almost disappears
```

With padding:

``` text
5×5

↓

5×5

↓

5×5

↓

Much more information retained
```

------------------------------------------------------------------------

# 8. Advantages

-   Preserves edge information.
-   Controls output dimensions.
-   Enables deeper CNNs.
-   Improves feature learning near borders.

------------------------------------------------------------------------

# 9. Python Implementation

TensorFlow:

``` python
from tensorflow.keras.layers import Conv2D

Conv2D(
    filters=32,
    kernel_size=(3,3),
    padding="same",
    activation="relu"
)
```

Valid padding:

``` python
padding="valid"
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Create a small grayscale image.
2.  Apply convolution without padding.
3.  Apply convolution with same padding.
4.  Compare output sizes.
5.  Visualize border preservation.

------------------------------------------------------------------------

# 11. Interview Questions

### What is padding?

Adding extra pixels around an image before convolution.

### Why is padding important?

It preserves spatial dimensions and edge information.

### Difference between valid and same padding?

-   Valid: No padding, output shrinks.
-   Same: Adds padding to preserve output size (for stride = 1).

### Which padding is most commonly used in CNNs?

Zero Padding.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Padding fundamentals.
-   Valid vs Same padding.
-   Zero, Reflection, and Replication padding.
-   Output dimension calculations.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 136 -- Stride**

You'll learn how stride controls the movement of convolution filters,
affects output size, influences computational cost, and works together
with padding to determine the spatial dimensions of feature maps.
