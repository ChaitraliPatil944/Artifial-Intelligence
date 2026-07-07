# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 152 -- Bidirectional RNNs

> **A Bidirectional Recurrent Neural Network (BiRNN) processes a
> sequence in both forward and backward directions. By combining
> information from the past and the future, it often produces better
> representations for tasks such as language understanding, speech
> recognition, and named entity recognition.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Bidirectional RNNs.
-   Learn why future context is useful.
-   Compare unidirectional and bidirectional RNNs.
-   Study Bidirectional LSTM and GRU.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  Why Bidirectional RNNs?
2.  Architecture
3.  Forward vs Backward Pass
4.  Information Flow
5.  Bidirectional LSTM
6.  Bidirectional GRU
7.  Advantages & Limitations
8.  Applications
9.  TensorFlow Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. Why Bidirectional RNNs?

A standard RNN only uses past context.

``` text
Past ─────► Present
```

A Bidirectional RNN uses both directions.

``` text
Past ───► Present ◄─── Future
```

This improves understanding when future words provide meaning.

------------------------------------------------------------------------

# 2. Architecture

``` text
            Forward RNN
x₁ → x₂ → x₃ → x₄

x₁ ← x₂ ← x₃ ← x₄
            Backward RNN

        │
Concatenate Outputs
        │
 Final Representation
```

The outputs from both directions are combined.

------------------------------------------------------------------------

# 3. Forward vs Backward Pass

  Forward RNN               Backward RNN
  ------------------------- ----------------------------
  Reads left → right        Reads right → left
  Uses previous context     Uses future context
  One hidden state stream   Second hidden state stream

------------------------------------------------------------------------

# 4. Information Flow

For every time step:

``` text
Forward Hidden State
          │
Backward Hidden State
          │
Concatenate
          │
Prediction
```

The model benefits from complete sequence context.

------------------------------------------------------------------------

# 5. Bidirectional LSTM

Replace each RNN with an LSTM.

Benefits:

-   Long-term memory
-   Past + future context
-   Better NLP performance

------------------------------------------------------------------------

# 6. Bidirectional GRU

Replace each RNN with a GRU.

Benefits:

-   Faster than BiLSTM
-   Fewer parameters
-   Strong sequence modeling

------------------------------------------------------------------------

# 7. Advantages & Limitations

## Advantages

-   Better context understanding
-   Improved accuracy
-   Effective for NLP and speech tasks

## Limitations

-   Higher computation
-   More memory usage
-   Not suitable for real-time prediction where future inputs are
    unavailable

------------------------------------------------------------------------

# 8. Applications

-   Machine Translation
-   Named Entity Recognition
-   Speech Recognition
-   Part-of-Speech Tagging
-   Question Answering
-   Medical text analysis

------------------------------------------------------------------------

# 9. TensorFlow Example

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Bidirectional, LSTM, Dense

model = Sequential([
    Bidirectional(LSTM(128), input_shape=(100,50)),
    Dense(5, activation="softmax")
])
```

Using a GRU:

``` python
from tensorflow.keras.layers import GRU

Bidirectional(GRU(64))
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Train a unidirectional LSTM.
2.  Train a Bidirectional LSTM.
3.  Compare:
    -   Accuracy
    -   Training time
    -   Parameter count
4.  Explain the trade-offs.

------------------------------------------------------------------------

# 11. Interview Questions

### What is a Bidirectional RNN?

An RNN that processes sequences in both forward and backward directions.

### Why does it improve performance?

Because it uses both past and future context.

### Can Bidirectional RNNs be used for live streaming?

Generally no, because future inputs are not yet available.

### Difference between BiLSTM and BiGRU?

BiLSTM uses LSTM cells; BiGRU uses GRU cells with fewer parameters.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Bidirectional processing.
-   Forward and backward RNNs.
-   BiLSTM and BiGRU.
-   Advantages and limitations.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 153 -- Sequence-to-Sequence (Seq2Seq) Models**

You'll learn encoder-decoder architectures, sequence generation, machine
translation, teacher forcing, inference, and how Seq2Seq models paved
the way for modern attention mechanisms and Transformers.
