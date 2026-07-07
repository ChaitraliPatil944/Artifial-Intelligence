# Chapter 9 -- Neural Networks

# Lesson 128 -- Batch Normalization

> **Batch Normalization (BatchNorm) is a technique that normalizes the
> inputs to each layer of a neural network during training. It
> stabilizes learning, allows higher learning rates, speeds up
> convergence, and often improves generalization. Introduced in 2015,
> BatchNorm became one of the most influential innovations in deep
> learning.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Batch Normalization.
-   Learn why it was introduced.
-   Understand Internal Covariate Shift.
-   Learn the BatchNorm algorithm.
-   Study γ (gamma) and β (beta) parameters.
-   Compare training and inference behavior.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Batch Normalization?
2.  Why BatchNorm?
3.  Internal Covariate Shift
4.  How BatchNorm Works
5.  Learnable Parameters (γ and β)
6.  Training vs Inference
7.  Where to Place BatchNorm
8.  Advantages
9.  Limitations
10. Python Implementation
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is Batch Normalization?

BatchNorm normalizes the activations of a layer using the statistics of
the current mini-batch.

``` text
Layer Output
      │
Normalize
      │
Scale & Shift
      │
Next Layer
```

This keeps the values entering the next layer well behaved.

------------------------------------------------------------------------

# 2. Why BatchNorm?

During training, the distribution of activations changes as weights are
updated.

This makes optimization harder.

BatchNorm reduces these shifts, allowing faster and more stable
learning.

------------------------------------------------------------------------

# 3. Internal Covariate Shift

``` text
Layer 1 Changes
       │
Layer 2 Input Changes
       │
Layer 3 Input Changes
       │
Training Slows
```

BatchNorm helps stabilize these changing distributions.

> **Note:** The original motivation emphasized reducing *internal
> covariate shift*. Modern research suggests BatchNorm's benefits also
> come from smoother optimization and better-conditioned gradients.

------------------------------------------------------------------------

# 4. How BatchNorm Works

For each mini-batch:

1.  Compute the batch mean.
2.  Compute the batch variance.
3.  Normalize the activations.
4.  Scale using γ (gamma).
5.  Shift using β (beta).

Workflow:

``` text
Mini-Batch
     │
Mean & Variance
     │
Normalize
     │
γ × x̂ + β
     │
Output
```

------------------------------------------------------------------------

# 5. Learnable Parameters (γ and β)

After normalization:

``` text
Normalized Output

↓

γ (Scale)

↓

β (Shift)
```

-   **γ (gamma):** Learns the appropriate scale.
-   **β (beta):** Learns the appropriate offset.

These parameters allow the network to recover useful distributions if
strict normalization is not optimal.

------------------------------------------------------------------------

# 6. Training vs Inference

### During Training

-   Uses the current mini-batch mean.
-   Uses the current mini-batch variance.

### During Inference

-   Uses moving averages collected during training.
-   Produces deterministic predictions.

------------------------------------------------------------------------

# 7. Where to Place BatchNorm

Typical architecture:

``` text
Dense / Conv

↓

BatchNorm

↓

ReLU

↓

Next Layer
```

Many modern architectures follow this pattern, though some variations
exist.

------------------------------------------------------------------------

# 8. Advantages

-   Faster convergence.
-   Allows higher learning rates.
-   More stable gradients.
-   Often reduces overfitting.
-   Less sensitive to initialization.

------------------------------------------------------------------------

# 9. Limitations

-   Depends on mini-batch statistics.
-   Less effective with very small batch sizes.
-   Can be less suitable for sequence models, where Layer Normalization
    is often preferred.

------------------------------------------------------------------------

# 10. Python Implementation

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense, BatchNormalization

model = Sequential([
    Dense(128),
    BatchNormalization(),
    Dense(64, activation="relu"),
    BatchNormalization(),
    Dense(10, activation="softmax")
])
```

------------------------------------------------------------------------

# 11. Mini Project

1.  Train a neural network without BatchNorm.
2.  Record training time and validation accuracy.
3.  Add BatchNormalization layers.
4.  Compare convergence speed.
5.  Plot training loss curves.

------------------------------------------------------------------------

# 12. Interview Questions

### What is Batch Normalization?

A technique that normalizes layer activations during training to improve
optimization.

### Why is BatchNorm useful?

It speeds up training, stabilizes gradients, and often improves
generalization.

### What are γ and β?

Trainable parameters that scale and shift normalized activations.

### Does BatchNorm behave the same during inference?

No. Training uses batch statistics, while inference uses moving
averages.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   Batch Normalization fundamentals.
-   Internal Covariate Shift.
-   γ and β parameters.
-   Training vs inference.
-   Advantages and limitations.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 129 -- Dropout**

You'll learn how Dropout prevents overfitting by randomly disabling
neurons during training, understand why it works, compare it with Batch
Normalization and Regularization, and explore its role in modern deep
learning models.
