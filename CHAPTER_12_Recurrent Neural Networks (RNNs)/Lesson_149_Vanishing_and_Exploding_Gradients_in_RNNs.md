# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 149 -- Vanishing & Exploding Gradients in RNNs

> **Vanishing and Exploding Gradients are two major problems encountered
> while training Recurrent Neural Networks using Backpropagation Through
> Time (BPTT). They make learning long-term dependencies difficult and
> were the primary motivation for developing LSTM and GRU
> architectures.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand vanishing and exploding gradients.
-   Learn why they occur.
-   Study their mathematical intuition.
-   Learn gradient clipping.
-   Understand why LSTMs and GRUs were invented.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What are Gradients?
2.  Vanishing Gradient Problem
3.  Exploding Gradient Problem
4.  Why They Occur
5.  Effect on Learning
6.  Solutions
7.  Gradient Clipping
8.  Why LSTMs Solve This
9.  TensorFlow Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What are Gradients?

Gradients tell the optimizer how much to update model parameters.

``` text
Loss
 │
Gradient
 │
Weight Update
```

Healthy gradients are essential for learning.

------------------------------------------------------------------------

# 2. Vanishing Gradient Problem

During BPTT:

``` text
1

↓

0.5

↓

0.25

↓

0.125

↓

0.06

↓

≈0
```

The gradient becomes extremely small.

Consequences:

-   Early layers stop learning.
-   Long-term dependencies are forgotten.
-   Training becomes slow.

------------------------------------------------------------------------

# 3. Exploding Gradient Problem

Instead of shrinking:

``` text
1

↓

2

↓

4

↓

8

↓

16

↓

256
```

The gradient grows uncontrollably.

Consequences:

-   Huge weight updates.
-   Numerical instability.
-   Training may diverge.

------------------------------------------------------------------------

# 4. Why They Occur

During BPTT, gradients are repeatedly multiplied across many time steps.

``` text
Gradient

×

Gradient

×

Gradient

×

...
```

If values are:

-   Less than 1 → Vanishing gradients.
-   Greater than 1 → Exploding gradients.

------------------------------------------------------------------------

# 5. Effect on Learning

``` text
Long Sequence

↓

Early Information

↓

Gradient Becomes Tiny

↓

Model Forgets
```

This is why a basic RNN struggles with long sentences or long
time-series.

------------------------------------------------------------------------

# 6. Solutions

Common approaches:

-   Better weight initialization
-   ReLU variants (where appropriate)
-   Gradient clipping
-   Batch/Layer normalization
-   LSTM
-   GRU

Modern architectures largely rely on LSTM, GRU, or Transformers.

------------------------------------------------------------------------

# 7. Gradient Clipping

Instead of allowing gradients to grow without bound:

``` text
Huge Gradient

↓

Clip

↓

Maximum Allowed Value
```

TensorFlow:

``` python
optimizer = tf.keras.optimizers.Adam(
    learning_rate=0.001,
    clipnorm=1.0
)
```

or

``` python
optimizer = tf.keras.optimizers.Adam(
    clipvalue=0.5
)
```

Gradient clipping is especially useful for exploding gradients.

------------------------------------------------------------------------

# 8. Why LSTMs Solve This

Basic RNN:

``` text
Memory

↓

Fades Away
```

LSTM:

``` text
Forget Gate

↓

Input Gate

↓

Output Gate

↓

Long-Term Memory
```

The cell state provides a more reliable path for gradients, helping
preserve information over long sequences.

------------------------------------------------------------------------

# 9. TensorFlow Example

``` python
from tensorflow.keras.layers import SimpleRNN

model = tf.keras.Sequential([
    SimpleRNN(64),
    tf.keras.layers.Dense(1)
])

optimizer = tf.keras.optimizers.Adam(
    learning_rate=0.001,
    clipnorm=1.0
)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Train a SimpleRNN on short sequences.
2.  Train it on much longer sequences.
3.  Compare convergence.
4.  Enable gradient clipping.
5.  Observe training stability.

------------------------------------------------------------------------

# 11. Interview Questions

### What is the vanishing gradient problem?

Gradients become extremely small during backpropagation, preventing
earlier time steps from learning.

### What is the exploding gradient problem?

Gradients become excessively large, causing unstable updates.

### Why do these problems occur in RNNs?

Because gradients are repeatedly multiplied across many time steps
during BPTT.

### How can exploding gradients be reduced?

Using gradient clipping.

### Which architectures were designed to overcome vanishing gradients?

LSTM and GRU.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Vanishing gradients.
-   Exploding gradients.
-   Mathematical intuition.
-   Gradient clipping.
-   Why LSTMs and GRUs were invented.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 150 -- Long Short-Term Memory (LSTM)**

You'll learn how LSTMs overcome the limitations of basic RNNs using
memory cells and gates, understand the Forget, Input, and Output Gates,
explore the Cell State, and build one of the most influential
architectures in sequence modeling.
