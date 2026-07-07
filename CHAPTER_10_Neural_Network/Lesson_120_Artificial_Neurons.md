# Chapter 9 -- Neural Networks

# Lesson 120 -- Artificial Neurons

> **An Artificial Neuron is the mathematical model of a biological
> neuron. It receives inputs, assigns importance using weights, combines
> them, adds a bias, and produces an output through an activation
> function. Every modern neural network is built from millions or even
> billions of these simple computational units.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what an Artificial Neuron is.
-   Learn why it was invented.
-   Study the McCulloch--Pitts Neuron.
-   Understand inputs, weights, bias and weighted sum.
-   Learn the role of activation functions.
-   Build intuition with numerical examples.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is an Artificial Neuron?
2.  Why was it Invented?
3.  McCulloch--Pitts Neuron
4.  Components of an Artificial Neuron
5.  Mathematical Model
6.  Step-by-Step Example
7.  Biological vs Artificial Neuron
8.  Python Implementation
9.  Applications
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is an Artificial Neuron?

An artificial neuron is the smallest computational unit in a neural
network.

``` text
Inputs
  │
Weights
  │
Weighted Sum
  │
+ Bias
  │
Activation Function
  │
Output
```

------------------------------------------------------------------------

# 2. Why was it Invented?

Researchers wanted a mathematical model that could imitate the
decision-making process of biological neurons.

Goals:

-   Learn patterns
-   Make predictions
-   Generalize from examples

------------------------------------------------------------------------

# 3. McCulloch--Pitts Neuron

Introduced in **1943**, it was the first mathematical neuron model.

``` text
Inputs
  │
Weighted Sum
  │
Threshold
  │
0 or 1
```

It inspired later models such as the Perceptron.

------------------------------------------------------------------------

# 4. Components of an Artificial Neuron

### Inputs (x)

Features supplied to the neuron.

``` text
x₁  x₂  x₃
```

### Weights (w)

Importance assigned to each input.

``` text
w₁  w₂  w₃
```

### Bias (b)

A constant that shifts the decision boundary.

### Weighted Sum

``` text
z = w₁x₁ + w₂x₂ + ... + wₙxₙ + b
```

### Activation Function

Converts the weighted sum into the final output.

------------------------------------------------------------------------

# 5. Mathematical Model

``` text
x₁ ──×w₁──\
x₂ ──×w₂───\
x₃ ──×w₃────► Σ + b ► Activation ► Output
```

Equation:

``` text
y = f(Σ(wx) + b)
```

where:

-   x = inputs
-   w = weights
-   b = bias
-   f = activation function

------------------------------------------------------------------------

# 6. Step-by-Step Example

Suppose:

``` text
x₁ = 2
x₂ = 3

w₁ = 0.5
w₂ = 0.8

b = 1
```

Weighted sum:

``` text
z

= (2 × 0.5)

+ (3 × 0.8)

+ 1

= 4.4
```

If the threshold is 3:

``` text
4.4 > 3

Output = 1
```

------------------------------------------------------------------------

# 7. Biological vs Artificial Neuron

  Biological   Artificial
  ------------ --------------
  Dendrites    Inputs
  Synapses     Weights
  Cell Body    Weighted Sum
  Threshold    Activation
  Axon         Output

------------------------------------------------------------------------

# 8. Python Implementation

``` python
import numpy as np

x = np.array([2, 3])
w = np.array([0.5, 0.8])
b = 1

z = np.dot(x, w) + b

output = 1 if z > 3 else 0

print(z)
print(output)
```

------------------------------------------------------------------------

# 9. Applications

-   Image classification
-   Speech recognition
-   Fraud detection
-   Recommendation systems
-   Large Language Models

------------------------------------------------------------------------

# 10. Mini Project

1.  Create a neuron with three inputs.
2.  Assign custom weights.
3.  Compute the weighted sum.
4.  Apply a threshold activation.
5.  Test with different inputs.

------------------------------------------------------------------------

# 11. Interview Questions

### What is an artificial neuron?

A mathematical model inspired by a biological neuron.

### What is the purpose of weights?

To represent the importance of each input.

### Why is bias needed?

To shift the decision boundary and improve learning flexibility.

### What is the output equation?

``` text
y = f(Σ(wx) + b)
```

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Artificial neuron fundamentals.
-   McCulloch--Pitts model.
-   Inputs, weights and bias.
-   Weighted sum.
-   Activation functions.
-   Python implementation.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 121 -- Perceptron**

You'll learn the first trainable neural network, understand the
Perceptron Learning Algorithm, decision boundaries, convergence,
limitations, and why it laid the foundation for modern deep learning.
