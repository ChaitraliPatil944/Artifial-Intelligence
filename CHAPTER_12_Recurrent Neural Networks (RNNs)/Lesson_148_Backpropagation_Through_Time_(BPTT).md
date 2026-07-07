# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 148 -- Backpropagation Through Time (BPTT)

> **Backpropagation Through Time (BPTT) is the training algorithm used
> for Recurrent Neural Networks. It extends ordinary backpropagation by
> unfolding an RNN across time, allowing gradients to flow through every
> time step so the shared parameters can be updated based on the entire
> sequence.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Backpropagation Through Time.
-   Learn why ordinary backpropagation is insufficient for RNNs.
-   Understand unrolling through time.
-   Study gradient flow across time steps.
-   Learn Truncated BPTT.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  Why BPTT?
2.  Recap of Backpropagation
3.  Unrolling an RNN
4.  Forward Pass
5.  Backward Pass
6.  Gradient Flow
7.  Weight Sharing
8.  Truncated BPTT
9.  Computational Challenges
10. TensorFlow Example
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. Why BPTT?

In a feedforward network, information moves only through layers.

In an RNN, information moves through:

-   Layers
-   Time

Therefore, gradients must also flow through both dimensions.

------------------------------------------------------------------------

# 2. Recap of Backpropagation

Feedforward training:

``` text
Input
  │
Forward Pass
  │
Loss
  │
Backpropagation
  │
Weight Update
```

This works because there are no recurrent connections.

------------------------------------------------------------------------

# 3. Unrolling an RNN

A recurrent loop is unfolded into multiple time steps.

``` text
t1        t2        t3

[RNN] → [RNN] → [RNN]

 x1        x2        x3
```

Each block uses the **same parameters**.

------------------------------------------------------------------------

# 4. Forward Pass

At every time step:

``` text
Input(t)

+

Hidden(t-1)

↓

Hidden(t)

↓

Output(t)
```

The hidden state carries information forward.

------------------------------------------------------------------------

# 5. Backward Pass

During training:

``` text
Loss(t3)

↑

Loss(t2)

↑

Loss(t1)

↑

Shared Weights Updated
```

The gradient is propagated backward through every previous time step.

------------------------------------------------------------------------

# 6. Gradient Flow

``` text
Output

↓

Loss

↓

Time Step 3

↓

Time Step 2

↓

Time Step 1

↓

Parameter Update
```

Early time steps receive gradients that have passed through many
computations.

------------------------------------------------------------------------

# 7. Weight Sharing

Unlike feedforward networks, an RNN uses one set of weights repeatedly.

``` text
Time1 ─┐
Time2 ─┼── Same Weights
Time3 ─┘
```

The gradients from all time steps are accumulated before updating the
shared parameters.

------------------------------------------------------------------------

# 8. Truncated BPTT

Very long sequences make training expensive.

Instead of propagating through the entire sequence:

``` text
1000 Steps

↓

Backpropagate only

20–50 Steps
```

Benefits:

-   Faster training
-   Lower memory usage

Trade-off:

-   Long-range dependencies may be harder to learn.

------------------------------------------------------------------------

# 9. Computational Challenges

BPTT faces several issues:

-   High memory usage
-   Slow sequential computation
-   Vanishing gradients
-   Exploding gradients

These motivated the development of LSTMs and GRUs.

------------------------------------------------------------------------

# 10. TensorFlow Example

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import SimpleRNN, Dense

model = Sequential([
    SimpleRNN(64, input_shape=(100, 50)),
    Dense(5, activation="softmax")
])

model.compile(
    optimizer="adam",
    loss="categorical_crossentropy",
    metrics=["accuracy"]
)
```

TensorFlow performs BPTT automatically during `model.fit()`.

------------------------------------------------------------------------

# 11. Mini Project

1.  Build a SimpleRNN.
2.  Train it on a sequence dataset.
3.  Observe training time as sequence length increases.
4.  Compare short and long sequences.
5.  Explain why training becomes more difficult.

------------------------------------------------------------------------

# 12. Interview Questions

### What is BPTT?

Backpropagation Through Time is the training algorithm for RNNs.

### Why can't ordinary backpropagation be used directly?

Because RNNs contain recurrent connections across time.

### Why are gradients accumulated across time steps?

Because the same weights are reused at every step.

### What is Truncated BPTT?

A technique that limits backpropagation to a fixed number of time steps
to reduce computational cost.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   Why BPTT is needed.
-   Unrolling through time.
-   Forward and backward passes.
-   Gradient flow.
-   Weight sharing.
-   Truncated BPTT.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 149 -- Vanishing & Exploding Gradients in RNNs**

You'll learn why gradients shrink or grow exponentially during BPTT, how
these problems affect learning, techniques like gradient clipping, and
why LSTMs and GRUs were invented to overcome these limitations.
