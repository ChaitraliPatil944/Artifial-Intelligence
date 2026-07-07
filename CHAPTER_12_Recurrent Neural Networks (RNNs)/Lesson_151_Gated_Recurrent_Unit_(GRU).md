# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 151 -- Gated Recurrent Unit (GRU)

> **The Gated Recurrent Unit (GRU) is a simplified version of the LSTM
> designed to learn long-term dependencies while using fewer parameters.
> By combining memory mechanisms into only two gates, GRUs often train
> faster than LSTMs while achieving comparable performance on many
> sequence modeling tasks.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what a GRU is.
-   Learn why GRUs were introduced.
-   Study the Update and Reset Gates.
-   Compare GRUs with LSTMs.
-   Learn when to use GRUs.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  Why GRU?
2.  History
3.  GRU Architecture
4.  Update Gate
5.  Reset Gate
6.  Information Flow
7.  GRU vs LSTM
8.  Advantages & Limitations
9.  TensorFlow Implementation
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. Why GRU?

Although LSTMs solved the vanishing gradient problem, they introduced a
more complex architecture.

GRUs simplify this by:

-   Removing the separate Cell State
-   Using only two gates
-   Reducing parameters
-   Training faster

------------------------------------------------------------------------

# 2. History

The **GRU** was introduced in **2014** by researchers at the University
of Montreal.

Goal:

-   Simpler than LSTM
-   Comparable performance
-   Lower computational cost

------------------------------------------------------------------------

# 3. GRU Architecture

``` text
Input x(t)
     │
 Reset Gate
     │
 Update Gate
     │
 Hidden State h(t)
```

Unlike LSTMs, there is **no separate Cell State**.

------------------------------------------------------------------------

# 4. Update Gate

The **Update Gate** decides how much previous information should be
retained.

``` text
Old Hidden State
        │
 Update Gate
        │
Keep or Replace
```

It combines the role of the Forget Gate and Input Gate found in LSTMs.

------------------------------------------------------------------------

# 5. Reset Gate

The **Reset Gate** determines how much past information should be
ignored when computing the new hidden state.

``` text
Past Memory
      │
 Reset Gate
      │
Relevant Information
```

This helps the GRU forget outdated context when necessary.

------------------------------------------------------------------------

# 6. Information Flow

``` text
x(t)
 │
 ▼
Reset Gate
 │
 ▼
Candidate Hidden State
 │
 ▼
Update Gate
 │
 ▼
New Hidden State
```

The hidden state serves as both short-term memory and long-term memory.

------------------------------------------------------------------------

# 7. GRU vs LSTM

  -----------------------------------------------------------------------
  LSTM                                   GRU
  -------------------------------------- --------------------------------
  3 Gates                                2 Gates

  Cell State + Hidden State              Hidden State only

  More parameters                        Fewer parameters

  Slightly slower                        Usually faster

  Better for very long sequences         Often similar performance with
                                         lower cost
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 8. Advantages & Limitations

## Advantages

-   Faster training
-   Fewer parameters
-   Easier to implement
-   Strong performance on many NLP and time-series tasks

## Limitations

-   Slightly less expressive than LSTM
-   Performance depends on dataset and task

------------------------------------------------------------------------

# 9. TensorFlow Implementation

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import GRU, Dense

model = Sequential([
    GRU(128, input_shape=(100, 50)),
    Dense(10, activation="softmax")
])

model.compile(
    optimizer="adam",
    loss="categorical_crossentropy",
    metrics=["accuracy"]
)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Train a GRU model on a sentiment analysis dataset.
2.  Train an equivalent LSTM model.
3.  Compare:
    -   Accuracy
    -   Training time
    -   Parameter count
4.  Explain which model is more suitable for your dataset.

------------------------------------------------------------------------

# 11. Interview Questions

### What is a GRU?

A simplified recurrent neural network architecture that uses gating
mechanisms to learn long-term dependencies.

### How many gates does a GRU have?

Two: the Update Gate and the Reset Gate.

### What is the biggest difference between GRU and LSTM?

GRUs do not use a separate Cell State.

### When would you choose a GRU?

When faster training and lower computational cost are important while
maintaining strong performance.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Why GRUs were introduced.
-   Update and Reset Gates.
-   Information flow inside a GRU.
-   GRU vs LSTM.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 152 -- Bidirectional RNNs**

You'll learn how Bidirectional RNNs process sequences in both forward
and backward directions, understand why future context can improve
predictions, compare them with unidirectional RNNs, and implement
Bidirectional LSTM and GRU models in TensorFlow.
