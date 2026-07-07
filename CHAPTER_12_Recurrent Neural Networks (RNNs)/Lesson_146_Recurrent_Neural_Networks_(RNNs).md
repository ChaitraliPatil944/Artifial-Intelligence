# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 146 -- Recurrent Neural Networks (RNNs)

> **A Recurrent Neural Network (RNN) is a neural network designed for
> sequential data. Unlike feedforward networks, an RNN maintains a
> hidden state (memory) that carries information from previous time
> steps, enabling it to understand context and temporal dependencies.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what an RNN is.
-   Learn why RNNs were invented.
-   Study recurrent connections.
-   Understand hidden states.
-   Learn parameter sharing.
-   Follow forward propagation through time.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is an RNN?
2.  Why RNNs?
3.  RNN Architecture
4.  Hidden State
5.  Recurrent Connections
6.  Unrolling Through Time
7.  Forward Propagation
8.  Parameter Sharing
9.  Advantages & Limitations
10. TensorFlow Implementation
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is an RNN?

An RNN processes one element of a sequence at a time while remembering
previous information.

``` text
Input(t)
   │
Hidden State
   │
Output(t)
```

------------------------------------------------------------------------

# 2. Why RNNs?

Many problems require memory.

Examples:

-   Language
-   Speech
-   Time-series
-   DNA sequences

Feedforward networks treat every input independently, while RNNs use
previous context.

------------------------------------------------------------------------

# 3. RNN Architecture

``` text
x₁ → [RNN] → y₁
        │
        ▼
x₂ → [RNN] → y₂
        │
        ▼
x₃ → [RNN] → y₃
```

The hidden state flows from one time step to the next.

------------------------------------------------------------------------

# 4. Hidden State

The hidden state stores information from previous inputs.

``` text
Current Input

+

Previous Hidden State

↓

New Hidden State
```

Think of it as the network's short-term memory.

------------------------------------------------------------------------

# 5. Recurrent Connections

Unlike feedforward networks, an RNN has a feedback loop.

``` text
Hidden State
     ▲
     │
Current Step
```

This loop allows information to persist across time.

------------------------------------------------------------------------

# 6. Unrolling Through Time

Although an RNN contains a loop, we visualize training by "unrolling"
it.

``` text
t=1      t=2      t=3

[RNN] → [RNN] → [RNN]

 x₁        x₂        x₃
```

Each block shares the same parameters.

------------------------------------------------------------------------

# 7. Forward Propagation

For each time step:

1.  Read current input.
2.  Combine it with the previous hidden state.
3.  Compute a new hidden state.
4.  Produce the output.

``` text
x(t) + h(t-1)

↓

RNN Cell

↓

h(t)

↓

y(t)
```

------------------------------------------------------------------------

# 8. Parameter Sharing

A major advantage of RNNs is that the **same weights** are reused at
every time step.

``` text
Time 1 ─┐
Time 2 ─┼── Same Parameters
Time 3 ─┘
```

Benefits:

-   Fewer parameters
-   Better generalization
-   Works with variable-length sequences

------------------------------------------------------------------------

# 9. Advantages & Limitations

## Advantages

-   Remembers previous information.
-   Handles variable-length sequences.
-   Suitable for language and time-series.

## Limitations

-   Difficult to learn long-term dependencies.
-   Suffers from vanishing and exploding gradients.
-   Sequential computation limits parallelism.

------------------------------------------------------------------------

# 10. TensorFlow Implementation

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import SimpleRNN, Dense

model = Sequential([
    SimpleRNN(64, input_shape=(100, 50)),
    Dense(10, activation="softmax")
])
```

------------------------------------------------------------------------

# 11. Mini Project

1.  Load a text dataset.
2.  Tokenize the sentences.
3.  Build a SimpleRNN model.
4.  Train it for sequence classification.
5.  Compare it with a feedforward model.

------------------------------------------------------------------------

# 12. Interview Questions

### What is an RNN?

A neural network designed for sequential data using recurrent
connections and hidden states.

### What is the hidden state?

The memory that carries information from previous time steps.

### Why are parameters shared?

To reduce model size and enable processing of sequences with different
lengths.

### What is the biggest weakness of a basic RNN?

Difficulty learning long-range dependencies due to vanishing gradients.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   RNN fundamentals.
-   Hidden states.
-   Recurrent connections.
-   Unrolling through time.
-   Parameter sharing.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 147 -- Hidden States & Memory**

You'll explore how hidden states evolve across a sequence, how
information is stored and updated, memory capacity, context propagation,
and why hidden states are the heart of every recurrent neural network.
