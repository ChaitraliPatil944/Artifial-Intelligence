# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 156 -- NLP Applications of RNNs

> **Natural Language Processing (NLP) enables computers to understand,
> interpret, and generate human language. Before the rise of
> Transformers, Recurrent Neural Networks (RNNs), LSTMs, and GRUs were
> the dominant architectures for solving NLP tasks because they could
> model the sequential nature of language.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand the role of RNNs in NLP.
-   Learn the NLP pipeline.
-   Study major NLP applications.
-   Understand text preprocessing.
-   Learn how LSTMs and GRUs are applied.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is NLP?
2.  Why RNNs for NLP?
3.  NLP Pipeline
4.  Text Preprocessing
5.  Word Embeddings (Introduction)
6.  Major NLP Applications
7.  TensorFlow Example
8.  Mini Project
9.  Interview Questions
10. Summary
11. What's Next?

------------------------------------------------------------------------

# 1. What is NLP?

Natural Language Processing (NLP) is a field of AI that enables
computers to process human language.

Examples:

-   Translation
-   Chatbots
-   Voice assistants
-   Search engines
-   Spam detection

------------------------------------------------------------------------

# 2. Why RNNs for NLP?

Language is sequential.

Example:

``` text
I love AI
```

Changing the order:

``` text
AI love I
```

changes the meaning completely.

RNNs process words in sequence while remembering previous words.

------------------------------------------------------------------------

# 3. NLP Pipeline

``` text
Raw Text
    │
Cleaning
    │
Tokenization
    │
Vocabulary
    │
Numerical Encoding
    │
Embeddings
    │
RNN / LSTM / GRU
    │
Prediction
```

------------------------------------------------------------------------

# 4. Text Preprocessing

Typical preprocessing:

-   Lowercasing
-   Removing punctuation
-   Tokenization
-   Removing stop words (task dependent)
-   Padding sequences
-   Numerical encoding

Example:

``` text
"I love AI"

↓

["i", "love", "ai"]

↓

[12, 43, 8]
```

------------------------------------------------------------------------

# 5. Word Embeddings (Introduction)

Instead of representing words as simple IDs:

``` text
Dog = 25
Cat = 31
```

Embeddings represent them as dense vectors.

``` text
Dog

↓

[0.23, -0.14, 0.82, ...]
```

Similar words have similar vector representations.

------------------------------------------------------------------------

# 6. Major NLP Applications

### Sentiment Analysis

``` text
Review

↓

Positive / Negative
```

------------------------------------------------------------------------

### Language Modeling

Predict the next word.

``` text
I love

↓

AI
```

------------------------------------------------------------------------

### Text Generation

Generate coherent sentences from a prompt.

------------------------------------------------------------------------

### Machine Translation

``` text
English

↓

French
```

------------------------------------------------------------------------

### Named Entity Recognition (NER)

Identify entities such as:

-   Person
-   Organization
-   Location

------------------------------------------------------------------------

### Part-of-Speech (POS) Tagging

Assign grammatical labels.

Example:

``` text
Dog → Noun

Run → Verb
```

------------------------------------------------------------------------

### Speech Recognition

Convert spoken language into text.

------------------------------------------------------------------------

# 7. TensorFlow Example

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Embedding, LSTM, Dense

model = Sequential([
    Embedding(input_dim=10000,
              output_dim=128),
    LSTM(128),
    Dense(1, activation="sigmoid")
])

model.compile(
    optimizer="adam",
    loss="binary_crossentropy",
    metrics=["accuracy"]
)
```

------------------------------------------------------------------------

# 8. Mini Project

1.  Load an IMDb sentiment dataset.
2.  Tokenize and pad sequences.
3.  Train an LSTM classifier.
4.  Evaluate accuracy.
5.  Predict the sentiment of custom reviews.

------------------------------------------------------------------------

# 9. Interview Questions

### Why were RNNs widely used for NLP?

Because language is sequential and RNNs can remember previous context.

### What is tokenization?

Splitting text into smaller units such as words or subwords.

### Why are embeddings better than integer IDs?

They capture semantic relationships between words.

### Name three NLP applications.

-   Sentiment Analysis
-   Machine Translation
-   Named Entity Recognition

------------------------------------------------------------------------

# 10. Summary

You learned:

-   NLP fundamentals.
-   NLP preprocessing pipeline.
-   Word embeddings.
-   Major NLP applications.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 11. What's Next?

**Lesson 157 -- RNN Project: Sentiment Analysis**

You'll build a complete sentiment analysis system using TensorFlow,
including preprocessing, tokenization, embeddings, LSTM modeling,
training, evaluation, prediction, and deployment-ready practices.
