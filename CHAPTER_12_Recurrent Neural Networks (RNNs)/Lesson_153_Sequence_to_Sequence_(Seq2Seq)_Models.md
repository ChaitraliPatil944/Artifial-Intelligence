# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 153 -- Sequence-to-Sequence (Seq2Seq) Models

> **Sequence-to-Sequence (Seq2Seq) models are neural architectures that
> transform one sequence into another. They introduced the
> Encoder--Decoder framework, making tasks like machine translation,
> summarization, dialogue systems, and speech recognition practical.
> Seq2Seq models also laid the foundation for the Attention Mechanism
> and modern Transformers.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Seq2Seq models.
-   Learn the Encoder--Decoder architecture.
-   Understand context vectors.
-   Study Teacher Forcing.
-   Learn Greedy Decoding and Beam Search.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  Why Seq2Seq?
2.  Encoder--Decoder Architecture
3.  Context Vector
4.  Training vs Inference
5.  Teacher Forcing
6.  Decoding Methods
7.  Applications
8.  Limitations
9.  TensorFlow Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. Why Seq2Seq?

Unlike ordinary classifiers:

``` text
Input → Output
```

Seq2Seq performs:

``` text
Input Sequence

↓

Output Sequence
```

Example:

``` text
English

↓

French
```

------------------------------------------------------------------------

# 2. Encoder--Decoder Architecture

``` text
Input Sentence

↓

Encoder

↓

Context Vector

↓

Decoder

↓

Output Sentence
```

The encoder reads the input sequence.

The decoder generates the output sequence one token at a time.

------------------------------------------------------------------------

# 3. Context Vector

The encoder compresses the entire input into one fixed-size vector.

``` text
Sentence

↓

Encoder

↓

Context Vector
```

The decoder uses this vector to begin generating the output.

------------------------------------------------------------------------

# 4. Training vs Inference

### Training

The decoder receives the correct previous word.

``` text
Correct Word

↓

Next Prediction
```

### Inference

The decoder must use its own prediction.

``` text
Prediction

↓

Next Prediction
```

Errors may accumulate during inference.

------------------------------------------------------------------------

# 5. Teacher Forcing

Teacher Forcing feeds the **true previous token** to the decoder during
training.

Benefits:

-   Faster convergence
-   More stable learning

Limitation:

The model becomes dependent on correct previous tokens.

------------------------------------------------------------------------

# 6. Decoding Methods

### Greedy Decoding

Always choose the most probable next word.

``` text
Highest Probability

↓

Next Token
```

Fast but not always optimal.

### Beam Search

Keeps several candidate sequences.

``` text
Candidate 1

Candidate 2

Candidate 3
```

Produces better translations at a higher computational cost.

------------------------------------------------------------------------

# 7. Applications

-   Machine Translation
-   Text Summarization
-   Chatbots
-   Speech Recognition
-   Question Answering
-   Code Generation

------------------------------------------------------------------------

# 8. Limitations

The fixed-size context vector becomes a bottleneck for long sequences.

``` text
Very Long Sentence

↓

Single Context Vector

↓

Information Loss
```

This limitation motivated the Attention Mechanism.

------------------------------------------------------------------------

# 9. TensorFlow Example

``` python
from tensorflow.keras.layers import LSTM

encoder = LSTM(128, return_state=True)
decoder = LSTM(128, return_sequences=True)
```

Modern TensorFlow implementations often use higher-level APIs or
Transformers, but the encoder--decoder idea remains the same.

------------------------------------------------------------------------

# 10. Mini Project

1.  Load a small English--French dataset.
2.  Build an encoder--decoder LSTM.
3.  Train with Teacher Forcing.
4.  Compare Greedy Decoding and Beam Search.
5.  Translate new sentences.

------------------------------------------------------------------------

# 11. Interview Questions

### What is a Seq2Seq model?

A neural network that converts one sequence into another.

### What are the two main components?

Encoder and Decoder.

### What is Teacher Forcing?

Using the correct previous output as input during training.

### Why were Attention mechanisms introduced?

To overcome the fixed-size context vector bottleneck.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Encoder--Decoder architecture.
-   Context vectors.
-   Teacher Forcing.
-   Greedy Decoding.
-   Beam Search.
-   Seq2Seq limitations.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 154 -- Attention Mechanism (Introduction)**

You'll learn how Attention allows a model to focus on the most relevant
parts of an input sequence instead of relying on a single context
vector, paving the way for Transformers and modern Large Language
Models.
