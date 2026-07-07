# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 154 -- Attention Mechanism (Introduction)

> **The Attention Mechanism allows a neural network to focus on the most
> relevant parts of an input sequence when producing each output.
> Instead of compressing an entire sequence into one fixed-size vector,
> attention dynamically assigns importance to different tokens,
> dramatically improving sequence modeling and forming the foundation of
> modern Transformers and Large Language Models.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand why Attention was invented.
-   Learn the Context Vector bottleneck.
-   Understand alignment scores.
-   Learn Query, Key and Value (high-level).
-   Compare Soft and Hard Attention.
-   Prepare for Transformers.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  Why Attention?
2.  Context Vector Bottleneck
3.  Basic Idea
4.  Alignment Scores
5.  Attention Weights
6.  Query, Key & Value
7.  Soft vs Hard Attention
8.  Applications
9.  TensorFlow Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. Why Attention?

Seq2Seq models encode an entire sentence into one vector.

``` text
Long Sentence
      │
 Encoder
      │
Single Context Vector
      │
 Decoder
```

For long sequences, important information can be lost.

------------------------------------------------------------------------

# 2. Context Vector Bottleneck

``` text
100 Words

↓

One Fixed Vector

↓

Information Compression

↓

Possible Information Loss
```

Attention removes this bottleneck by letting the decoder revisit the
encoder outputs.

------------------------------------------------------------------------

# 3. Basic Idea

Instead of remembering everything equally:

``` text
Input Words

↓

Find Important Words

↓

Focus More

↓

Generate Output
```

For translating:

> "The black cat sat on the mat."

When generating **"cat"**, the decoder pays more attention to **"cat"**
than unrelated words.

------------------------------------------------------------------------

# 4. Alignment Scores

The decoder computes a score for every encoder output.

``` text
Decoder State

↓

Compare with Every Encoder State

↓

Alignment Scores
```

Higher score = more relevant.

------------------------------------------------------------------------

# 5. Attention Weights

Alignment scores are converted into probabilities.

``` text
Scores

↓

Softmax

↓

Attention Weights

↓

Weighted Sum

↓

Context Vector
```

The new context vector is created dynamically for each output token.

------------------------------------------------------------------------

# 6. Query, Key & Value

High-level intuition:

  Component   Purpose
  ----------- ------------------------
  Query (Q)   What I'm looking for
  Key (K)     What each input offers
  Value (V)   Information returned

``` text
Query

↓

Compare with Keys

↓

Attention Scores

↓

Weighted Values

↓

Output
```

These ideas become central in Transformers.

------------------------------------------------------------------------

# 7. Soft vs Hard Attention

  -----------------------------------------------------------------------
  Soft Attention                      Hard Attention
  ----------------------------------- -----------------------------------
  Attends to all inputs with          Selects only specific inputs
  different weights                   

  Differentiable                      Usually non-differentiable

  Most common                         Less common
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 8. Applications

-   Machine Translation
-   Text Summarization
-   Question Answering
-   Speech Recognition
-   Image Captioning
-   Large Language Models

------------------------------------------------------------------------

# 9. TensorFlow Example

``` python
from tensorflow.keras.layers import Attention

attention = Attention()

context = attention([query, value])
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Build a Seq2Seq model.
2.  Add an Attention layer.
3.  Compare translation accuracy.
4.  Visualize attention weights.
5.  Explain why attention improves long sequences.

------------------------------------------------------------------------

# 11. Interview Questions

### Why was Attention introduced?

To overcome the fixed-size context vector limitation in Seq2Seq models.

### What does Attention compute?

The importance of each input element for the current prediction.

### What are Query, Key and Value?

Query searches, Keys describe inputs, Values contain returned
information.

### Why is Attention important?

It forms the foundation of Transformers, BERT, GPT and modern LLMs.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Why Attention was invented.
-   Context vector bottleneck.
-   Alignment scores.
-   Attention weights.
-   Query, Key and Value.
-   Applications.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 155 -- Time Series Forecasting with RNNs**

You'll learn how RNNs, LSTMs and GRUs are applied to forecasting
sequential numerical data, including windowing, sequence preparation,
multistep prediction, evaluation metrics, and real-world applications
such as stock prices, weather prediction, and sensor analytics.
