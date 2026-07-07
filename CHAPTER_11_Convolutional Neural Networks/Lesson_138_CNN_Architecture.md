# Chapter 10 -- Convolutional Neural Networks (CNNs)

# Lesson 138 -- CNN Architecture

> **A Convolutional Neural Network (CNN) Architecture is a structured
> arrangement of layers that progressively transforms raw image pixels
> into high-level features and finally into predictions. By combining
> convolution, activation, pooling, and fully connected layers, CNNs can
> automatically learn visual patterns from data.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand the complete CNN architecture.
-   Learn the role of every layer.
-   Study the end-to-end data flow.
-   Understand parameter flow.
-   Learn why CNNs outperform dense networks for images.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is a CNN Architecture?
2.  End-to-End CNN Pipeline
3.  Input Layer
4.  Convolution Layer
5.  Activation Layer
6.  Pooling Layer
7.  Flatten Layer
8.  Fully Connected Layer
9.  Output Layer
10. Complete Forward Pass
11. Python Implementation
12. Mini Project
13. Interview Questions
14. Summary
15. What's Next?

------------------------------------------------------------------------

# 1. What is a CNN Architecture?

A CNN architecture is an organized sequence of layers that extracts
increasingly complex image features before making a prediction.

``` text
Image
  │
CNN Layers
  │
Prediction
```

------------------------------------------------------------------------

# 2. End-to-End CNN Pipeline

``` text
Input Image
      │
Convolution
      │
ReLU
      │
Pooling
      │
Convolution
      │
ReLU
      │
Pooling
      │
Flatten
      │
Dense Layer
      │
Softmax
      │
Prediction
```

Each stage performs a different task.

------------------------------------------------------------------------

# 3. Input Layer

The input layer receives the image.

Example:

``` text
224 × 224 × 3
```

This represents:

-   Height
-   Width
-   RGB Channels

------------------------------------------------------------------------

# 4. Convolution Layer

The convolution layer extracts local patterns.

Examples:

-   Edges
-   Corners
-   Textures

Output:

``` text
Feature Maps
```

------------------------------------------------------------------------

# 5. Activation Layer

Typically uses:

``` text
ReLU
```

Purpose:

-   Introduces non-linearity.
-   Enables learning of complex patterns.

------------------------------------------------------------------------

# 6. Pooling Layer

Pooling reduces feature map size.

Example:

``` text
32 × 32

↓

16 × 16
```

Benefits:

-   Faster computation
-   Lower memory usage
-   Better robustness

------------------------------------------------------------------------

# 7. Flatten Layer

Feature maps are converted into a single vector.

Example:

``` text
16 × 16 × 64

↓

16384 values
```

This vector becomes the input to dense layers.

------------------------------------------------------------------------

# 8. Fully Connected Layer

Dense layers combine extracted features to perform classification.

``` text
Flattened Features
      │
Dense
      │
Dense
      │
Prediction
```

------------------------------------------------------------------------

# 9. Output Layer

The final layer depends on the task.

Binary Classification:

``` text
Sigmoid
```

Multi-Class Classification:

``` text
Softmax
```

Regression:

``` text
Linear
```

------------------------------------------------------------------------

# 10. Complete Forward Pass

``` text
Image
  │
Conv
  │
ReLU
  │
Pooling
  │
Conv
  │
ReLU
  │
Pooling
  │
Flatten
  │
Dense
  │
Output
```

As depth increases:

``` text
Edges

↓

Textures

↓

Object Parts

↓

Objects

↓

Prediction
```

------------------------------------------------------------------------

# 11. Python Implementation

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import (
    Conv2D,
    MaxPooling2D,
    Flatten,
    Dense
)

model = Sequential([
    Conv2D(32, (3,3), activation="relu", input_shape=(224,224,3)),
    MaxPooling2D((2,2)),
    Conv2D(64, (3,3), activation="relu"),
    MaxPooling2D((2,2)),
    Flatten(),
    Dense(128, activation="relu"),
    Dense(10, activation="softmax")
])

model.summary()
```

------------------------------------------------------------------------

# 12. Mini Project

1.  Build the CNN shown above.
2.  Train it on a simple image dataset (e.g., CIFAR-10 or MNIST).
3.  Observe the model summary.
4.  Plot training and validation accuracy.
5.  Experiment with additional convolution layers.

------------------------------------------------------------------------

# 13. Interview Questions

### What are the main layers in a CNN?

Input, Convolution, Activation, Pooling, Flatten, Dense, and Output.

### Why is the Flatten layer needed?

It converts multi-dimensional feature maps into a one-dimensional vector
for dense layers.

### Which activation is commonly used in hidden CNN layers?

ReLU.

### Why are pooling layers used?

To reduce feature map dimensions, computation, and overfitting.

------------------------------------------------------------------------

# 14. Summary

You learned:

-   Complete CNN architecture.
-   Role of each layer.
-   End-to-end data flow.
-   Forward propagation.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 15. What's Next?

**Lesson 139 -- Famous CNN Architectures**

You'll explore landmark CNN models including LeNet, AlexNet, VGG,
GoogLeNet (Inception), ResNet, DenseNet, EfficientNet, and MobileNet,
understanding how each advanced computer vision and influenced modern
deep learning.
