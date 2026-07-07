# Chapter 10 -- Convolutional Neural Networks (CNNs)

# Lesson 136 -- Stride

> **Stride is the number of pixels a convolution filter moves after each
> operation. It controls how densely the filter scans an image, directly
> affecting the output size, computational cost, and the amount of
> visual information retained. Choosing the right stride is a balance
> between accuracy and efficiency.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what Stride is.
-   Learn why Stride is needed.
-   Compare different stride values.
-   Calculate output dimensions using stride.
-   Understand the relationship between stride and padding.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Stride?
2.  Why Stride is Needed
3.  How Stride Works
4.  Output Size Formula
5.  Stride vs Padding
6.  Effect of Different Stride Values
7.  Computational Trade-offs
8.  Python Implementation
9.  Mini Project
10. Interview Questions
11. Summary
12. What's Next?

------------------------------------------------------------------------

# 1. What is Stride?

Stride is the distance that a convolution filter moves across an image
after processing one position.

``` text
Stride = 1

□■■■□
□■■■□
□■■■□

↓

Move 1 Pixel →
```

A larger stride skips more pixels.

------------------------------------------------------------------------

# 2. Why Stride is Needed

If the filter moved only one pixel forever:

-   Computation would be expensive.
-   Processing large images would be slow.

Stride helps reduce:

-   Computation
-   Memory usage
-   Feature map size

------------------------------------------------------------------------

# 3. How Stride Works

### Stride = 1

``` text
Image

□□□□□

↓

Every adjacent position is visited.
```

Produces the largest possible feature map.

### Stride = 2

``` text
Image

□□□□□

↓

Move two pixels each step.
```

Some positions are skipped, producing a smaller feature map.

------------------------------------------------------------------------

# 4. Output Size Formula

The output dimension of a convolution layer is:

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

### Example

Input:

``` text
32 × 32
```

Kernel:

``` text
3 × 3
```

Padding:

``` text
1
```

Stride:

``` text
2
```

Calculation:

``` text
((32 - 3 + 2×1) / 2) + 1

=

16
```

So the output becomes:

``` text
16 × 16
```

------------------------------------------------------------------------

# 5. Stride vs Padding

  Stride                     Padding
  -------------------------- ----------------------------
  Controls filter movement   Adds border pixels
  Reduces output size        Preserves output size
  Reduces computation        Preserves edge information

Together, they determine the final feature map dimensions.

------------------------------------------------------------------------

# 6. Effect of Different Stride Values

  Stride   Output Size   Speed     Information
  -------- ------------- --------- -----------------------
  1        Large         Slower    Highest detail
  2        Medium        Faster    Moderate detail
  3+       Small         Fastest   More information loss

Choosing a very large stride may cause important features to be skipped.

------------------------------------------------------------------------

# 7. Computational Trade-offs

``` text
Small Stride

↓

More Computation

↓

Higher Accuracy Potential

----------------------------

Large Stride

↓

Less Computation

↓

Lower Memory Usage

↓

Possible Information Loss
```

CNN designers choose stride based on the task and available resources.

------------------------------------------------------------------------

# 8. Python Implementation

TensorFlow example:

``` python
from tensorflow.keras.layers import Conv2D

layer = Conv2D(
    filters=32,
    kernel_size=(3,3),
    strides=(2,2),
    padding="same",
    activation="relu"
)
```

This layer moves the filter two pixels horizontally and vertically.

------------------------------------------------------------------------

# 9. Mini Project

1.  Create a CNN with stride = 1.
2.  Record the output feature map size.
3.  Change the stride to 2.
4.  Compare the output dimensions.
5.  Measure the effect on training speed.

------------------------------------------------------------------------

# 10. Interview Questions

### What is stride?

The number of pixels a convolution filter moves after each operation.

### What happens when stride increases?

The output feature map becomes smaller, computation decreases, and some
information may be lost.

### Does stride affect the number of filters?

No. It changes the spatial dimensions of the output, not the number of
filters.

### How do stride and padding work together?

Stride controls movement, while padding controls the border and helps
preserve spatial dimensions.

------------------------------------------------------------------------

# 11. Summary

You learned:

-   What stride is.
-   Why it is used.
-   Output dimension calculations.
-   Relationship with padding.
-   Computational trade-offs.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 12. What's Next?

**Lesson 137 -- Pooling Layers**

You'll learn how pooling reduces feature map size, understand Max
Pooling and Average Pooling, discover why pooling improves translation
robustness, and explore how it helps CNNs become more efficient while
preserving important features.
