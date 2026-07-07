# Chapter 9 -- Neural Networks

# Lesson 127 -- Optimizers

> **An optimizer is an algorithm that updates a neural network's weights
> using the gradients computed by backpropagation. While Gradient
> Descent provides the basic update rule, modern optimizers improve
> training speed, stability, and convergence by adapting how updates are
> made.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what optimizers are.
-   Learn why Gradient Descent alone is not always enough.
-   Study AdaGrad, RMSProp, Adam, AdamW, and Nadam.
-   Learn adaptive learning rates.
-   Compare optimizers.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is an Optimizer?
2.  Why Modern Optimizers?
3.  AdaGrad
4.  RMSProp
5.  Adam
6.  AdamW
7.  Nadam
8.  Optimizer Comparison
9.  Choosing the Right Optimizer
10. Python Implementation
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is an Optimizer?

An optimizer updates model parameters to reduce the loss.

``` text
Prediction
   │
Loss
   │
Backpropagation
   │
Gradients
   │
Optimizer
   │
Updated Weights
```

Without an optimizer, the gradients would never be applied.

------------------------------------------------------------------------

# 2. Why Modern Optimizers?

Standard Gradient Descent can be:

-   Slow
-   Sensitive to learning rate
-   Unstable on complex loss surfaces

Modern optimizers improve convergence and training stability.

------------------------------------------------------------------------

# 3. AdaGrad

**Adaptive Gradient** adjusts the learning rate for each parameter.

Advantages:

-   Good for sparse data
-   Automatic learning rate adaptation

Disadvantages:

-   Learning rate can become extremely small over time.

Best for:

-   Sparse features
-   NLP problems

------------------------------------------------------------------------

# 4. RMSProp

RMSProp fixes AdaGrad's rapidly shrinking learning rate.

It keeps a moving average of squared gradients.

Advantages:

-   Faster convergence
-   Stable learning
-   Excellent for recurrent neural networks

------------------------------------------------------------------------

# 5. Adam (Adaptive Moment Estimation)

Adam combines:

``` text
Momentum
      +
RMSProp
```

Advantages:

-   Fast convergence
-   Adaptive learning rates
-   Robust default choice
-   Works well on many tasks

This is the most commonly used optimizer in deep learning.

------------------------------------------------------------------------

# 6. AdamW

AdamW separates weight decay from gradient updates.

Advantages:

-   Better regularization
-   Improved generalization
-   Popular in Transformer models

------------------------------------------------------------------------

# 7. Nadam

Nadam combines:

-   Adam
-   Nesterov Momentum

Advantages:

-   Faster convergence in some problems
-   Better look-ahead optimization

------------------------------------------------------------------------

# 8. Optimizer Comparison

  Optimizer   Adaptive LR   Momentum   Typical Use
  ----------- ------------- ---------- ---------------------------
  SGD         No            Optional   Simple models
  AdaGrad     Yes           No         Sparse data
  RMSProp     Yes           No         Deep & recurrent networks
  Adam        Yes           Yes        General deep learning
  AdamW       Yes           Yes        Transformers & modern DL
  Nadam       Yes           Yes        Faster convergence

------------------------------------------------------------------------

# 9. Choosing the Right Optimizer

``` text
Beginner
   │
Adam

Sparse Features
   │
AdaGrad

Transformers
   │
AdamW

Need Simplicity
   │
SGD
```

There is no universally best optimizer. The choice depends on the
problem and dataset.

------------------------------------------------------------------------

# 10. Python Implementation

``` python
from tensorflow.keras.optimizers import SGD, RMSprop, Adam, AdamW

model.compile(
    optimizer=Adam(learning_rate=0.001),
    loss="categorical_crossentropy",
    metrics=["accuracy"]
)
```

Other examples:

``` python
SGD(learning_rate=0.01, momentum=0.9)

RMSprop(learning_rate=0.001)

AdamW(learning_rate=0.001, weight_decay=1e-4)
```

------------------------------------------------------------------------

# 11. Mini Project

1.  Train a neural network using SGD.
2.  Train the same model using Adam.
3.  Compare loss curves.
4.  Train with RMSProp.
5.  Explain which optimizer converges fastest.

------------------------------------------------------------------------

# 12. Interview Questions

### What is an optimizer?

An algorithm that updates weights to minimize the loss function.

### Which optimizer is most commonly used?

Adam.

### Why is Adam popular?

It combines Momentum and adaptive learning rates, making it fast and
stable.

### When should AdamW be preferred?

For modern deep learning models, especially Transformer architectures
where proper weight decay is important.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   What optimizers are.
-   AdaGrad.
-   RMSProp.
-   Adam.
-   AdamW.
-   Nadam.
-   How to choose an optimizer.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 128 -- Batch Normalization**

You'll learn how Batch Normalization stabilizes training, reduces
internal covariate shift, enables higher learning rates, accelerates
convergence, and improves deep neural network performance.
