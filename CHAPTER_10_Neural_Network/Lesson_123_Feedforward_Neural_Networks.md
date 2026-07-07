# Chapter 9 -- Neural Networks

# Lesson 123 -- Feedforward Neural Networks (FNN)

> **A Feedforward Neural Network (FNN) is the simplest type of
> artificial neural network where information flows in only one
> direction, from the input layer to the output layer. There are no
> loops or feedback connections. Feedforward Neural Networks form the
> foundation of almost every modern deep learning architecture.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what a Feedforward Neural Network is.
-   Learn why FNNs were developed.
-   Study input, hidden, and output layers.
-   Understand forward propagation.
-   Learn about fully connected (dense) layers.
-   Understand the Universal Approximation Theorem.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is a Feedforward Neural Network?
2.  Why was it Developed?
3.  Network Architecture
4.  Types of Layers
5.  Forward Propagation
6.  Fully Connected Layers
7.  Universal Approximation Theorem
8.  Advantages
9.  Limitations
10. Python Implementation
11. Applications
12. Mini Project
13. Interview Questions
14. Summary
15. What's Next?

------------------------------------------------------------------------

# 1. What is a Feedforward Neural Network?

In an FNN, data moves only forward.

``` text
Input

↓

Hidden Layer

↓

Hidden Layer

↓

Output
```

No information flows backward during prediction.

------------------------------------------------------------------------

# 2. Why was it Developed?

A single neuron can solve only simple problems.

By connecting many neurons into layers, neural networks can learn highly
complex patterns.

------------------------------------------------------------------------

# 3. Network Architecture

``` text
Input Layer

○ ○ ○ ○

↓

Hidden Layer

● ● ● ●

↓

Hidden Layer

● ● ●

↓

Output Layer

◉
```

Every neuron connects to neurons in the next layer.

------------------------------------------------------------------------

# 4. Types of Layers

### Input Layer

Receives raw features.

Example:

``` text
Age

Salary

Experience
```

------------------------------------------------------------------------

### Hidden Layers

Perform feature extraction.

Every hidden layer learns increasingly abstract representations.

------------------------------------------------------------------------

### Output Layer

Produces the final prediction.

Examples:

Regression:

``` text
House Price
```

Classification:

``` text
Cat

Dog

Bird
```

------------------------------------------------------------------------

# 5. Forward Propagation

Forward propagation is the process of computing predictions.

``` text
Inputs

↓

Weighted Sum

↓

Activation

↓

Next Layer

↓

Output
```

Each neuron performs:

``` text
z = wx + b

↓

Activation(z)
```

This repeats layer by layer until the final prediction is produced.

------------------------------------------------------------------------

# 6. Fully Connected (Dense) Layers

In a dense layer:

Every neuron connects to every neuron in the next layer.

``` text
○ ○ ○

╲│╱╲│╱

● ●

╲│╱

◉
```

Advantages:

-   Learns complex relationships.
-   Flexible.
-   Widely used.

Disadvantage:

-   Large number of parameters.

------------------------------------------------------------------------

# 7. Universal Approximation Theorem

A neural network with:

-   At least one hidden layer
-   Enough neurons
-   Suitable activation functions

can approximate almost any continuous function.

This explains why neural networks are so powerful.

------------------------------------------------------------------------

# 8. Advantages

-   Learns non-linear relationships.
-   Highly flexible.
-   Works across many domains.
-   Foundation of deep learning.

------------------------------------------------------------------------

# 9. Limitations

-   Large computational cost.
-   Many trainable parameters.
-   Can overfit.
-   Requires substantial training data.

------------------------------------------------------------------------

# 10. Python Implementation

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense

model = Sequential([
    Dense(16, activation="relu", input_shape=(4,)),
    Dense(8, activation="relu"),
    Dense(1, activation="sigmoid")
])

model.summary()
```

------------------------------------------------------------------------

# 11. Applications

-   Image classification
-   Fraud detection
-   Medical diagnosis
-   Customer churn prediction
-   Recommendation systems

------------------------------------------------------------------------

# 12. Mini Project

1.  Build a simple Feedforward Neural Network.
2.  Use two hidden layers.
3.  Train on a binary classification dataset.
4.  Compare different numbers of hidden neurons.
5.  Measure model accuracy.

------------------------------------------------------------------------

# 13. Interview Questions

### What is a Feedforward Neural Network?

A neural network where information flows only from input to output.

### Why is it called "feedforward"?

Because there are no cycles or feedback connections.

### What is a hidden layer?

A layer between the input and output that learns intermediate
representations.

### What is a dense layer?

A layer where every neuron connects to every neuron in the next layer.

------------------------------------------------------------------------

# 14. Summary

You learned:

-   Feedforward Neural Networks.
-   Network architecture.
-   Hidden layers.
-   Forward propagation.
-   Dense layers.
-   Universal Approximation Theorem.
-   Python implementation.

------------------------------------------------------------------------

# 15. What's Next?

**Lesson 124 -- Loss Functions**

You'll learn how neural networks measure prediction errors using loss
functions, understand Binary Cross-Entropy, Categorical Cross-Entropy,
Mean Squared Error, Mean Absolute Error, Hinge Loss, and discover how
loss drives the learning process during training.
