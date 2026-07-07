# Chapter 9 -- Neural Networks

# Lesson 121 -- Perceptron

> **The Perceptron is the first trainable artificial neural network.
> Proposed by Frank Rosenblatt in 1958, it introduced the revolutionary
> idea that a machine could automatically learn by adjusting its weights
> based on errors. Modern deep learning traces its roots back to this
> simple yet powerful model.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what a Perceptron is.
-   Learn why it was invented.
-   Study the Perceptron architecture.
-   Understand the Perceptron Learning Algorithm.
-   Learn weight updates and learning rate.
-   Understand linear separability and the XOR problem.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is a Perceptron?
2.  History
3.  Why was it Invented?
4.  Perceptron Architecture
5.  Mathematical Model
6.  Perceptron Learning Algorithm
7.  Weight Update Rule
8.  Learning Rate
9.  Decision Boundary
10. Linear vs Non-linear Problems
11. XOR Limitation
12. Python Example
13. Applications
14. Mini Project
15. Interview Questions
16. Summary
17. What's Next?

------------------------------------------------------------------------

# 1. What is a Perceptron?

A Perceptron is a **single artificial neuron that can learn**.

Unlike the McCulloch--Pitts neuron, whose weights are fixed, the
Perceptron updates its weights automatically.

``` text
Inputs
   │
Weights
   │
Weighted Sum
   │
Activation
   │
Prediction
```

------------------------------------------------------------------------

# 2. History

``` text
1943
McCulloch–Pitts Model
        │
1958
Frank Rosenblatt
        │
Perceptron
        │
1986
Backpropagation
        │
Modern Deep Learning
```

The Perceptron was one of the earliest learning algorithms.

------------------------------------------------------------------------

# 3. Why was it Invented?

Researchers wanted machines that could:

-   Learn from data
-   Improve with experience
-   Adapt automatically

Instead of manually choosing weights, the Perceptron learns them.

------------------------------------------------------------------------

# 4. Perceptron Architecture

``` text
x₁ ─×w₁─\
x₂ ─×w₂──► Σ + b ► Step Function ► Output
x₃ ─×w₃─/
```

Components:

-   Inputs
-   Weights
-   Bias
-   Weighted Sum
-   Activation Function
-   Output

------------------------------------------------------------------------

# 5. Mathematical Model

Weighted sum:

``` text
z = w₁x₁ + w₂x₂ + ... + wₙxₙ + b
```

Prediction:

``` text
y = 1   if z ≥ 0

y = 0   otherwise
```

------------------------------------------------------------------------

# 6. Perceptron Learning Algorithm

Training process:

``` text
Initialize Weights
        │
Predict
        │
Compare with Actual
        │
Compute Error
        │
Update Weights
        │
Repeat
```

The process continues until errors are minimized or a maximum number of
iterations is reached.

------------------------------------------------------------------------

# 7. Weight Update Rule

The Perceptron updates its weights using:

``` text
New Weight

=

Old Weight

+

Learning Rate × Error × Input
```

Formula:

``` text
w = w + η × (y_true − y_pred) × x
```

where:

-   η (eta) = Learning Rate
-   Error = Actual − Predicted

------------------------------------------------------------------------

# 8. Learning Rate

The learning rate controls how much weights change after each mistake.

``` text
Small η

↓

Slow Learning
```

``` text
Large η

↓

Fast Learning

May Overshoot
```

Choosing the right learning rate is important.

------------------------------------------------------------------------

# 9. Decision Boundary

The Perceptron separates classes using a straight line (or hyperplane).

``` text
Class A

● ● ●

-----------

○ ○ ○

Class B
```

It can only learn **linear decision boundaries**.

------------------------------------------------------------------------

# 10. Linear vs Non-linear Problems

### Linearly Separable

``` text
● ● ●

--------

○ ○ ○
```

Perceptron works well.

### Non-linearly Separable

``` text
● ○

○ ●
```

Perceptron fails.

------------------------------------------------------------------------

# 11. XOR Limitation

The famous XOR problem:

  Input A   Input B   Output
  --------- --------- --------
  0         0         0
  0         1         1
  1         0         1
  1         1         0

No single straight line can separate these classes.

This limitation led to **Multi-Layer Perceptrons (MLPs)** and eventually
deep neural networks.

------------------------------------------------------------------------

# 12. Python Example

``` python
from sklearn.linear_model import Perceptron

model = Perceptron()

model.fit(X_train, y_train)

print(model.score(X_test, y_test))
```

------------------------------------------------------------------------

# 13. Applications

-   Binary classification
-   Pattern recognition
-   Simple classifiers
-   Educational demonstrations
-   Foundation for deep learning

------------------------------------------------------------------------

# 14. Mini Project

1.  Load a binary classification dataset.
2.  Train a Perceptron.
3.  Measure accuracy.
4.  Visualize the decision boundary.
5.  Try an XOR dataset and observe the failure.

------------------------------------------------------------------------

# 15. Interview Questions

### What is a Perceptron?

The first trainable artificial neural network.

### Who invented the Perceptron?

Frank Rosenblatt in 1958.

### Can a Perceptron solve XOR?

No. XOR is not linearly separable.

### What is the Perceptron Learning Rule?

``` text
w = w + η × (y_true − y_pred) × x
```

------------------------------------------------------------------------

# 16. Summary

You learned:

-   Perceptron fundamentals.
-   Learning algorithm.
-   Weight updates.
-   Learning rate.
-   Decision boundaries.
-   XOR limitation.
-   Python implementation.

------------------------------------------------------------------------

# 17. What's Next?

**Lesson 122 -- Activation Functions**

You'll learn why activation functions are essential, understand Step,
Sigmoid, Tanh, ReLU, Leaky ReLU, ELU, Softmax, and compare when each
should be used in modern neural networks.
