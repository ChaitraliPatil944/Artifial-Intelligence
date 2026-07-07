# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 147 -- Hidden States & Memory

> **The hidden state is the memory of a Recurrent Neural Network. At
> every time step, it stores useful information from previous inputs and
> combines it with the current input to produce a new hidden state. This
> ability to carry context across time makes RNNs fundamentally
> different from feedforward neural networks.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand hidden states.
-   Learn how memory works in RNNs.
-   Study hidden state updates.
-   Distinguish hidden state from cell state.
-   Understand information flow through time.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is a Hidden State?
2.  Why Memory is Needed
3.  Information Flow
4.  Updating the Hidden State
5.  Hidden State Dimensions
6.  Hidden State vs Cell State
7.  Short vs Long-Term Memory
8.  TensorFlow Example
9.  Mini Project
10. Interview Questions
11. Summary
12. What's Next?

------------------------------------------------------------------------

# 1. What is a Hidden State?

The hidden state is an internal vector that summarizes everything the
RNN has learned so far.

``` text
Input(t)

+

Hidden State(t−1)

↓

Hidden State(t)

↓

Output(t)
```

It is passed from one time step to the next.

------------------------------------------------------------------------

# 2. Why Memory is Needed

Consider:

``` text
The weather today is ...

↓

sunny
```

The meaning of the current word depends on the previous words.

Without memory:

``` text
Each word

↓

Independent prediction
```

With memory:

``` text
Previous Context

↓

Better prediction
```

------------------------------------------------------------------------

# 3. Information Flow

``` text
x₁ ─► h₁ ─► y₁
        │
        ▼
x₂ ─► h₂ ─► y₂
        │
        ▼
x₃ ─► h₃ ─► y₃
```

Every hidden state carries information from earlier time steps.

------------------------------------------------------------------------

# 4. Updating the Hidden State

At every time step the RNN performs:

1.  Read the current input.
2.  Combine it with the previous hidden state.
3.  Compute the new hidden state.
4.  Produce the output.

Conceptually:

``` text
New Memory

=

Old Memory

+

Current Information
```

The network decides this using learned weights.

------------------------------------------------------------------------

# 5. Hidden State Dimensions

If an RNN has:

``` text
128 hidden units
```

then each hidden state is a vector of length:

``` text
128
```

Larger hidden states can store more information but require more
computation.

------------------------------------------------------------------------

# 6. Hidden State vs Cell State

  Hidden State          Cell State
  --------------------- ----------------------------
  Used in basic RNNs    Introduced in LSTMs
  Short-term memory     Long-term memory
  Passed to next step   Passed through memory cell
  Produces outputs      Helps preserve information

We'll study cell states in the LSTM lesson.

------------------------------------------------------------------------

# 7. Short vs Long-Term Memory

``` text
Recent Information
      │
Easy to Remember

Old Information
      │
May Fade Away
```

Basic RNNs struggle to remember information from far back in a sequence,
leading to the vanishing gradient problem.

------------------------------------------------------------------------

# 8. TensorFlow Example

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import SimpleRNN

model = Sequential([
    SimpleRNN(
        units=128,
        return_sequences=True,
        input_shape=(100,50)
    )
])
```

`return_sequences=True` returns a hidden-state output for every time
step.

------------------------------------------------------------------------

# 9. Mini Project

1.  Build a SimpleRNN.
2.  Change hidden units from 32 to 64 to 128.
3.  Compare parameter counts.
4.  Observe training performance.
5.  Explain how hidden-state size affects capacity.

------------------------------------------------------------------------

# 10. Interview Questions

### What is a hidden state?

The internal memory of an RNN that carries information across time
steps.

### Why is it important?

It preserves context from previous inputs.

### Does every time step have a hidden state?

Yes. Each time step computes a new hidden state.

### Is the hidden state the same as the LSTM cell state?

No. LSTMs introduce a separate cell state for improved long-term memory.

------------------------------------------------------------------------

# 11. Summary

You learned:

-   Hidden state fundamentals.
-   Memory in RNNs.
-   Information flow.
-   Hidden-state updates.
-   Hidden state vs cell state.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 12. What's Next?

**Lesson 148 -- Backpropagation Through Time (BPTT)**

You'll learn how RNNs are trained by unfolding them through time, how
gradients flow across time steps, why training recurrent networks is
harder than feedforward networks, and how BPTT leads to vanishing and
exploding gradients.
