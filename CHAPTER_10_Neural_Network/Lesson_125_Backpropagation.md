# Chapter 9 -- Neural Networks

# Lesson 125 -- Backpropagation

> **Backpropagation is the learning algorithm that enables neural
> networks to improve themselves. It computes how much each weight
> contributed to the prediction error and updates those weights to
> reduce future errors. Combined with Gradient Descent, backpropagation
> powers almost every modern deep learning model.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Backpropagation.
-   Learn the forward and backward pass.
-   Understand gradients and the Chain Rule.
-   Learn how weights are updated.
-   Understand why backpropagation is efficient.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Backpropagation?
2.  Why was it Invented?
3.  Forward Pass
4.  Backward Pass
5.  Gradients
6.  Chain Rule
7.  Weight Update Rule
8.  Complete Algorithm
9.  Vanishing & Exploding Gradients
10. Python Example
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is Backpropagation?

Backpropagation computes how every weight affected the prediction error.

``` text
Prediction
    │
Loss
    │
Backpropagation
    │
Updated Weights
```

------------------------------------------------------------------------

# 2. Why was it Invented?

Early neural networks could make predictions but could not efficiently
learn.

Backpropagation solved this by efficiently calculating gradients for
every parameter.

------------------------------------------------------------------------

# 3. Forward Pass

Information flows from input to output.

``` text
Input
  │
Hidden Layers
  │
Output
  │
Loss
```

The network first predicts before learning.

------------------------------------------------------------------------

# 4. Backward Pass

The error flows backwards.

``` text
Loss
  │
Output Layer
  │
Hidden Layer
  │
Input Side
```

Each layer receives information about how much it contributed to the
error.

------------------------------------------------------------------------

# 5. Gradients

A gradient measures how much the loss changes when a weight changes.

``` text
Large Gradient

↓

Large Weight Update

Small Gradient

↓

Small Weight Update
```

------------------------------------------------------------------------

# 6. Chain Rule

Backpropagation uses the Chain Rule from calculus.

``` text
Input
 │
Layer 1
 │
Layer 2
 │
Loss
```

Gradient at one layer depends on all later layers.

Conceptually:

``` text
dLoss/dw

=

(dLoss/dOutput)

×

(dOutput/dz)

×

(dz/dw)
```

------------------------------------------------------------------------

# 7. Weight Update Rule

``` text
New Weight

=

Old Weight

−

Learning Rate × Gradient
```

Formula:

``` text
w = w − η × ∂Loss/∂w
```

where η is the learning rate.

------------------------------------------------------------------------

# 8. Complete Algorithm

``` text
Initialize Weights
        │
Forward Pass
        │
Compute Loss
        │
Backward Pass
        │
Compute Gradients
        │
Update Weights
        │
Repeat
```

This repeats for many epochs until the loss decreases.

------------------------------------------------------------------------

# 9. Vanishing & Exploding Gradients

### Vanishing Gradient

Gradients become extremely small.

Effects:

-   Slow learning
-   Deep layers stop updating

Common solutions:

-   ReLU
-   Batch Normalization
-   Residual Connections

### Exploding Gradient

Gradients become extremely large.

Effects:

-   Unstable training
-   Huge weight updates

Common solutions:

-   Gradient Clipping
-   Better initialization
-   Lower learning rate

------------------------------------------------------------------------

# 10. Python Example

``` python
import tensorflow as tf

model.compile(
    optimizer="adam",
    loss="binary_crossentropy",
    metrics=["accuracy"]
)

model.fit(X_train, y_train, epochs=20)
```

TensorFlow automatically performs forward propagation, backpropagation,
and weight updates.

------------------------------------------------------------------------

# 11. Mini Project

1.  Build a small neural network.
2.  Train it for multiple epochs.
3.  Plot training loss.
4.  Observe how loss decreases.
5.  Experiment with different learning rates.

------------------------------------------------------------------------

# 12. Interview Questions

### What is Backpropagation?

An algorithm that computes gradients and updates neural network weights
to reduce prediction error.

### Why is the Chain Rule important?

It efficiently computes gradients through multiple layers.

### What is the difference between forward and backward propagation?

Forward propagation makes predictions. Backpropagation computes
gradients and updates weights.

### Does Backpropagation update weights directly?

No. It computes gradients, which are then used by an optimizer such as
Gradient Descent or Adam.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   Forward propagation.
-   Backward propagation.
-   Gradients.
-   Chain Rule.
-   Weight update rule.
-   Vanishing and exploding gradients.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 126 -- Gradient Descent Variants**

You'll learn Batch Gradient Descent, Stochastic Gradient Descent (SGD),
Mini-Batch Gradient Descent, momentum-based optimization, convergence
behavior, and why different optimization strategies dramatically affect
training speed and stability.
