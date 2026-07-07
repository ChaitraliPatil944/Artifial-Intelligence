# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 144 -- Introduction to Sequential Data

> **Sequential Data is data where the order of observations matters.
> Unlike images or tabular datasets, each element in a sequence depends
> on previous or future elements. Understanding sequential data is the
> foundation for learning Recurrent Neural Networks (RNNs), LSTMs, GRUs,
> Transformers, and modern Large Language Models.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what sequential data is.
-   Learn why order matters.
-   Compare sequential and non-sequential data.
-   Explore different sequence types.
-   Study real-world applications.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Sequential Data?
2.  Why Order Matters
3.  Sequential vs Non-Sequential Data
4.  Types of Sequences
5.  Examples from Real Life
6.  Challenges in Sequential Data
7.  Sequence Representation
8.  Applications
9.  Python Examples
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is Sequential Data?

Sequential data is information arranged in a meaningful order.

``` text
A → B → C → D
```

Changing the order changes the meaning.

Examples:

-   Sentences
-   Audio
-   Stock prices
-   Weather records
-   Sensor readings
-   DNA sequences

------------------------------------------------------------------------

# 2. Why Order Matters

Sentence 1:

``` text
The dog chased the cat.
```

Sentence 2:

``` text
The cat chased the dog.
```

The same words appear, but the meaning changes because of their order.

Likewise:

``` text
₹100 → ₹120 → ₹140
```

suggests growth, while

``` text
₹140 → ₹120 → ₹100
```

suggests decline.

------------------------------------------------------------------------

# 3. Sequential vs Non-Sequential Data

  Non-Sequential Data         Sequential Data
  --------------------------- -----------------------------
  Order usually unimportant   Order is essential
  Tabular data                Text, speech, time series
  Samples often independent   Samples depend on context
  Dense/CNN models            RNN/LSTM/Transformer models

------------------------------------------------------------------------

# 4. Types of Sequences

### One-to-One

``` text
Image → Label
```

### One-to-Many

``` text
Image → Caption
```

### Many-to-One

``` text
Sentence → Sentiment
```

### Many-to-Many

``` text
English Sentence → French Sentence
```

or

``` text
Word → Part of Speech
```

------------------------------------------------------------------------

# 5. Examples from Real Life

``` text
Stock Prices
Day1 → Day2 → Day3
```

``` text
Weather
Mon → Tue → Wed
```

``` text
Speech
Sound1 → Sound2 → Sound3
```

``` text
Typing
H → He → Hel → Hello
```

------------------------------------------------------------------------

# 6. Challenges in Sequential Data

-   Variable sequence lengths
-   Long-term dependencies
-   Missing values
-   Noise
-   High computational cost
-   Maintaining context over time

These challenges motivated specialized neural architectures.

------------------------------------------------------------------------

# 7. Sequence Representation

Example sentence:

``` text
"I love AI"
```

Tokenized:

``` text
["I", "love", "AI"]
```

Converted to numbers:

``` text
[15, 203, 91]
```

Later chapters will transform these numbers into embeddings.

------------------------------------------------------------------------

# 8. Applications

-   Machine Translation
-   Speech Recognition
-   Sentiment Analysis
-   Chatbots
-   Time-Series Forecasting
-   DNA Analysis
-   Predictive Maintenance

------------------------------------------------------------------------

# 9. Python Example

``` python
sequence = [10, 12, 15, 18, 21]

for value in sequence:
    print(value)
```

Simple tokenization:

``` python
sentence = "I love AI"

tokens = sentence.split()

print(tokens)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Load a text dataset.
2.  Split sentences into words.
3.  Count sequence lengths.
4.  Plot the distribution of sequence lengths.
5.  Explain why padding may be required.

------------------------------------------------------------------------

# 11. Interview Questions

### What is sequential data?

Data in which the order of observations carries important information.

### Give three examples.

-   Text
-   Speech
-   Stock prices

### Why can't order be ignored?

Because changing the order changes the meaning or underlying pattern.

### Which deep learning models are designed for sequential data?

RNNs, LSTMs, GRUs, and Transformers.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Sequential data fundamentals.
-   Why order matters.
-   Sequence types.
-   Applications.
-   Challenges.
-   Basic Python examples.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 145 -- Why Feedforward Networks Fail for Sequences**

You'll discover why ordinary feedforward neural networks cannot
effectively model temporal dependencies, understand the absence of
memory, and learn why recurrent architectures were invented.
