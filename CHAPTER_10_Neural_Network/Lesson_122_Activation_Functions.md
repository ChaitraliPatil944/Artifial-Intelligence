# Chapter 9 -- Neural Networks

# Lesson 122 -- Activation Functions

> **An Activation Function determines whether a neuron should "fire" by
> transforming its weighted input into an output. Without activation
> functions, even a network with hundreds of layers would behave like a
> simple linear model. Activation functions introduce non-linearity,
> allowing neural networks to solve complex real-world problems.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand why activation functions are needed.
-   Learn the difference between linear and non-linear models.
-   Study the most important activation functions.
-   Understand when to use each activation.
-   Learn their advantages, disadvantages, and mathematical intuition.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is an Activation Function?
2.  Why Activation Functions?
3.  Linear vs Non-linear Networks
4.  Step Function
5.  Linear Activation
6.  Sigmoid
7.  Tanh
8.  ReLU
9.  Leaky ReLU
10. ELU
11. Softmax
12. Comparison Table
13. Python Implementation
14. Applications
15. Mini Project
16. Interview Questions
17. Summary
18. What's Next?

------------------------------------------------------------------------

# 1. What is an Activation Function?

An activation function transforms the weighted sum of a neuron into its
final output.

``` text
Inputs
   │
Weights
   │
Weighted Sum
   │
Activation Function
   │
Output
```

Without this step, a neuron is simply performing linear arithmetic.

------------------------------------------------------------------------

# 2. Why Activation Functions?

Imagine stacking ten linear layers:

``` text
Linear
   │
Linear
   │
Linear
   │
Linear
```

The result is still **one linear transformation**.

Adding activation functions introduces **non-linearity**, enabling the
network to learn:

-   Images
-   Speech
-   Language
-   Complex decision boundaries

------------------------------------------------------------------------

# 3. Linear vs Non-linear Networks

### Without Activation

``` text
Input

↓

Linear

↓

Linear

↓

Linear

↓

Output
```

Equivalent to:

``` text
Input

↓

One Linear Layer

↓

Output
```

### With Activation

``` text
Input

↓

Linear

↓

ReLU

↓

Linear

↓

Sigmoid

↓

Output
```

Now the network can learn highly complex patterns.

------------------------------------------------------------------------

# 4. Step Function

Formula:

``` text
f(x)=1 if x≥0
f(x)=0 otherwise
```

Characteristics:

-   Binary output
-   Used in the Perceptron
-   Not differentiable
-   Not suitable for deep learning

------------------------------------------------------------------------

# 5. Linear Activation

Formula:

``` text
f(x)=x
```

Advantages:

-   Simple

Disadvantages:

-   Cannot learn non-linear relationships.

Usually used only in the **output layer of regression models**.

------------------------------------------------------------------------

# 6. Sigmoid

Formula:

``` text
f(x)=1/(1+e^-x)
```

Range:

``` text
0 → 1
```

Advantages:

-   Probability interpretation.
-   Smooth.

Disadvantages:

-   Vanishing gradient.
-   Slow convergence.

Best use:

-   Binary classification output layer.

------------------------------------------------------------------------

# 7. Tanh

Formula:

``` text
tanh(x)
```

Range:

``` text
-1 → 1
```

Advantages:

-   Zero-centered outputs.
-   Better than Sigmoid in many hidden layers.

Disadvantages:

-   Still suffers from vanishing gradients.

------------------------------------------------------------------------

# 8. ReLU (Rectified Linear Unit)

Formula:

``` text
f(x)=max(0,x)
```

Graph:

``` text
      /
     /
----/
```

Advantages:

-   Fast.
-   Computationally efficient.
-   Reduces vanishing gradients.
-   Default choice for hidden layers.

Disadvantages:

-   Dead ReLU problem (neurons can stop updating).

------------------------------------------------------------------------

# 9. Leaky ReLU

Formula:

``` text
x      if x>0

0.01x  otherwise
```

Advantages:

-   Prevents dead neurons.
-   Improves gradient flow.

Used when standard ReLU causes inactive neurons.

------------------------------------------------------------------------

# 10. ELU (Exponential Linear Unit)

Advantages:

-   Smooth negative values.
-   Faster convergence than ReLU in some tasks.
-   Reduces bias shift.

Disadvantage:

-   Slightly more computationally expensive.

------------------------------------------------------------------------

# 11. Softmax

Softmax converts outputs into probabilities that sum to 1.

Example:

``` text
Cat   0.80

Dog   0.15

Bird  0.05
```

Total:

``` text
1.00
```

Best use:

-   Multi-class classification output layer.

------------------------------------------------------------------------

# 12. Comparison Table

  Function     Range          Common Use
  ------------ -------------- --------------------------------
  Step         0 or 1         Perceptron
  Linear       (-∞,∞)         Regression Output
  Sigmoid      (0,1)          Binary Output
  Tanh         (-1,1)         Hidden Layers (older networks)
  ReLU         \[0,∞)         Hidden Layers (default)
  Leaky ReLU   (-∞,∞)         Hidden Layers
  ELU          (-∞,∞)         Deep Networks
  Softmax      0--1 (sum=1)   Multi-class Output

------------------------------------------------------------------------

# 13. Python Implementation

``` python
import tensorflow as tf

relu = tf.keras.layers.ReLU()

sigmoid = tf.keras.activations.sigmoid

softmax = tf.keras.activations.softmax

tanh = tf.keras.activations.tanh
```

------------------------------------------------------------------------

# 14. Applications

-   Image classification
-   Object detection
-   Speech recognition
-   NLP
-   Recommendation systems
-   Large Language Models

------------------------------------------------------------------------

# 15. Mini Project

1.  Create a simple neural network.
2.  Train using Sigmoid.
3.  Train using ReLU.
4.  Compare convergence speed.
5.  Replace output activation with Softmax for multiclass
    classification.

------------------------------------------------------------------------

# 16. Interview Questions

### Why are activation functions necessary?

They introduce non-linearity, allowing neural networks to learn complex
patterns.

### Why is ReLU widely used?

It is simple, efficient, and reduces the vanishing gradient problem.

### When should Softmax be used?

For multi-class classification output layers.

### Which activation is commonly used for binary classification output?

Sigmoid.

------------------------------------------------------------------------

# 17. Summary

You learned:

-   Why activation functions are needed.
-   Linear vs non-linear models.
-   Step, Linear, Sigmoid, Tanh, ReLU, Leaky ReLU, ELU, and Softmax.
-   When to use each activation function.
-   Python implementation.

------------------------------------------------------------------------

# 18. What's Next?

**Lesson 123 -- Feedforward Neural Networks**

You'll learn how individual neurons are connected into layers,
understand input, hidden, and output layers, forward propagation,
network architecture, and how complete neural networks make predictions.
