# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 150 -- Long Short-Term Memory (LSTM)

> **Long Short-Term Memory (LSTM) is a specialized Recurrent Neural
> Network architecture designed to overcome the vanishing gradient
> problem. It introduces a memory cell and gating mechanisms that allow
> the network to selectively remember, forget, and output information
> over long sequences.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand why LSTM was invented.
-   Learn the structure of an LSTM cell.
-   Differentiate Hidden State and Cell State.
-   Study Forget, Input, and Output Gates.
-   Understand information flow through an LSTM.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  Why LSTM?
2.  History
3.  LSTM Architecture
4.  Cell State vs Hidden State
5.  Forget Gate
6.  Input Gate
7.  Output Gate
8.  Complete Data Flow
9.  LSTM vs RNN
10. TensorFlow Example
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. Why LSTM?

Basic RNNs forget information from long sequences because of vanishing
gradients.

``` text
Long Sequence

↓

Basic RNN

↓

Memory Fades
```

LSTM was designed to preserve important information for much longer.

------------------------------------------------------------------------

# 2. History

LSTM was introduced in **1997** by:

-   Sepp Hochreiter
-   Jürgen Schmidhuber

Its goal was to solve long-term dependency problems in RNNs.

------------------------------------------------------------------------

# 3. LSTM Architecture

``` text
Input x(t)
      │
 Forget Gate
      │
 Input Gate
      │
 Cell State
      │
 Output Gate
      │
Hidden State h(t)
```

The cell state acts like a conveyor belt carrying long-term information.

------------------------------------------------------------------------

# 4. Cell State vs Hidden State

  Cell State                      Hidden State
  ------------------------------- --------------------------------
  Long-term memory                Short-term memory
  Flows through entire sequence   Used for current output
  Updated by gates                Passed to next step and output

------------------------------------------------------------------------

# 5. Forget Gate

The Forget Gate decides what information should be discarded.

``` text
Previous Cell State
        │
Forget Gate
        │
Keep / Remove Information
```

Example:

A chatbot may forget the topic from ten paragraphs ago if it is no
longer useful.

------------------------------------------------------------------------

# 6. Input Gate

The Input Gate determines what new information should be stored.

``` text
Current Input

↓

Input Gate

↓

Update Cell State
```

Only useful information is written into memory.

------------------------------------------------------------------------

# 7. Output Gate

The Output Gate decides what part of the memory should become the hidden
state.

``` text
Cell State

↓

Output Gate

↓

Hidden State
```

The hidden state is then passed to the next time step and used to
produce predictions.

------------------------------------------------------------------------

# 8. Complete Data Flow

``` text
x(t)
 │
 ▼
Forget Gate
 │
 ▼
Input Gate
 │
 ▼
Updated Cell State
 │
 ▼
Output Gate
 │
 ▼
h(t)
```

The three gates work together to control the flow of information.

------------------------------------------------------------------------

# 9. LSTM vs Basic RNN

  Basic RNN                          LSTM
  ---------------------------------- --------------------------------
  Single hidden state                Hidden state + Cell state
  Suffers from vanishing gradients   Handles long-term dependencies
  Simple architecture                Gate-based architecture
  Limited memory                     Long-term memory

------------------------------------------------------------------------

# 10. TensorFlow Example

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import LSTM, Dense

model = Sequential([
    LSTM(128, input_shape=(100, 50)),
    Dense(10, activation="softmax")
])

model.compile(
    optimizer="adam",
    loss="categorical_crossentropy",
    metrics=["accuracy"]
)
```

------------------------------------------------------------------------

# 11. Mini Project

1.  Load a sentiment analysis dataset.
2.  Build an LSTM classifier.
3.  Compare its accuracy with a SimpleRNN.
4.  Measure training time.
5.  Explain the difference in long-sequence performance.

------------------------------------------------------------------------

# 12. Interview Questions

### Why was LSTM invented?

To solve the vanishing gradient problem and learn long-term
dependencies.

### What are the three gates?

Forget Gate, Input Gate, and Output Gate.

### What is the Cell State?

The long-term memory of an LSTM.

### Difference between Cell State and Hidden State?

The Cell State stores long-term information, while the Hidden State
represents the current output and short-term context.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   Why LSTMs were created.
-   Cell State and Hidden State.
-   Forget, Input, and Output Gates.
-   Complete LSTM information flow.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 151 -- Gated Recurrent Unit (GRU)**

You'll learn how GRUs simplify LSTMs by combining gates, compare GRUs
with LSTMs, understand update and reset gates, and discover when GRUs
are preferred in practice.
