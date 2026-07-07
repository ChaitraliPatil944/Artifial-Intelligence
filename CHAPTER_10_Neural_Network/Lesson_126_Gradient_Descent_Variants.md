# Chapter 9 -- Neural Networks

# Lesson 126 -- Gradient Descent Variants

> **Gradient Descent is an optimization algorithm that updates a model's
> parameters to minimize the loss function. While Backpropagation
> computes the gradients, Gradient Descent decides how those gradients
> are used to move toward the minimum loss. Different variants trade off
> speed, stability, and computational cost.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Gradient Descent.
-   Differentiate Backpropagation and Gradient Descent.
-   Learn Batch, Stochastic, and Mini-Batch Gradient Descent.
-   Understand Momentum and Nesterov Momentum.
-   Learn convergence behavior and learning rate effects.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Gradient Descent?
2.  Why Optimization is Needed
3.  Backpropagation vs Gradient Descent
4.  Cost Function Landscape
5.  Batch Gradient Descent
6.  Stochastic Gradient Descent (SGD)
7.  Mini-Batch Gradient Descent
8.  Learning Rate
9.  Momentum
10. Nesterov Momentum
11. Comparison Table
12. Python Example
13. Mini Project
14. Interview Questions
15. Summary
16. What's Next?

------------------------------------------------------------------------

# 1. What is Gradient Descent?

Gradient Descent minimizes the loss by repeatedly updating model
weights.

``` text
Current Weights
      │
Compute Gradient
      │
Update Weights
      │
Lower Loss
```

------------------------------------------------------------------------

# 2. Why Optimization is Needed?

Training starts with random weights.

``` text
Random Weights
      │
High Loss
      │
Optimization
      │
Better Weights
```

Without optimization, the network would never improve.

------------------------------------------------------------------------

# 3. Backpropagation vs Gradient Descent

  Backpropagation      Gradient Descent
  -------------------- ----------------------------------
  Computes gradients   Uses gradients to update weights
  Uses Chain Rule      Uses optimization rule
  Tells direction      Takes the step

Think of it like this:

``` text
Backpropagation → Map

Gradient Descent → Walking
```

------------------------------------------------------------------------

# 4. Cost Function Landscape

``` text
Loss ↑

      ● Start
     /
    /
   /
 _/__________ Minimum

Parameters →
```

Goal: reach the minimum loss.

------------------------------------------------------------------------

# 5. Batch Gradient Descent

Uses the **entire dataset** before updating weights.

Advantages: - Stable updates - Accurate gradients

Disadvantages: - Slow - High memory usage

------------------------------------------------------------------------

# 6. Stochastic Gradient Descent (SGD)

Updates weights after **every training example**.

Advantages: - Fast updates - Escapes shallow local minima

Disadvantages: - Noisy learning - Less stable

------------------------------------------------------------------------

# 7. Mini-Batch Gradient Descent

Uses a small batch (e.g., 32, 64, 128 samples).

``` text
Dataset

↓

Mini Batches

↓

Update

↓

Repeat
```

Advantages: - Efficient - Stable - GPU friendly

This is the most common approach in deep learning.

------------------------------------------------------------------------

# 8. Learning Rate

Weight update:

``` text
w = w − η × Gradient
```

-   Small η → Slow convergence
-   Large η → May overshoot
-   Good η → Fast and stable learning

------------------------------------------------------------------------

# 9. Momentum

Momentum remembers previous updates.

``` text
Previous Direction
       +
Current Gradient
       ↓
Smoother Updates
```

Benefits: - Faster convergence - Reduces oscillation

------------------------------------------------------------------------

# 10. Nesterov Momentum

Nesterov looks **ahead** before updating.

Benefits: - More accurate updates - Faster convergence than standard
Momentum

------------------------------------------------------------------------

# 11. Comparison Table

  Variant         Update Frequency       Speed    Stability
  --------------- ---------------------- -------- -----------
  Batch GD        Whole dataset          Slow     High
  SGD             One sample             Fast     Low
  Mini-Batch GD   Small batch            Fast     High
  Momentum        Any GD + memory        Faster   Higher
  Nesterov        Momentum + lookahead   Faster   Very High

------------------------------------------------------------------------

# 12. Python Example

``` python
from tensorflow.keras.optimizers import SGD

optimizer = SGD(
    learning_rate=0.01,
    momentum=0.9,
    nesterov=True
)

model.compile(
    optimizer=optimizer,
    loss="categorical_crossentropy",
    metrics=["accuracy"]
)
```

------------------------------------------------------------------------

# 13. Mini Project

1.  Train a neural network using SGD.
2.  Repeat using Momentum.
3.  Compare convergence speed.
4.  Repeat with Mini-Batch training.
5.  Plot loss curves.

------------------------------------------------------------------------

# 14. Interview Questions

### What is Gradient Descent?

An optimization algorithm that minimizes loss by updating model
parameters.

### Difference between Backpropagation and Gradient Descent?

Backpropagation computes gradients; Gradient Descent applies them.

### Which Gradient Descent variant is most commonly used?

Mini-Batch Gradient Descent.

### Why use Momentum?

To accelerate convergence and reduce oscillations.

------------------------------------------------------------------------

# 15. Summary

You learned:

-   Gradient Descent fundamentals.
-   Batch, SGD, and Mini-Batch GD.
-   Learning rate.
-   Momentum and Nesterov Momentum.
-   Python implementation.

------------------------------------------------------------------------

# 16. What's Next?

**Lesson 127 -- Optimizers**

You'll explore modern optimizers including AdaGrad, RMSProp, Adam,
AdamW, Nadam, and understand why Adam became the default optimizer for
many deep learning applications.
