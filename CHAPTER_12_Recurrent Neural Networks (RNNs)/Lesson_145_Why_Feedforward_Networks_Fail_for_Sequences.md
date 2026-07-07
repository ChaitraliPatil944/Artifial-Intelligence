# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 145 -- Why Feedforward Networks Fail for Sequences

> **Feedforward Neural Networks process every input independently. They
> have no memory of previous inputs, making them unsuitable for
> sequential data such as language, speech, and time series where
> context and order are essential. These limitations led to the
> invention of Recurrent Neural Networks (RNNs).**

------------------------------------------------------------------------

# Learning Objectives

-   Understand why feedforward networks fail on sequential data.
-   Learn the importance of memory and context.
-   Study fixed-length input limitations.
-   Understand temporal dependencies.
-   Build intuition for why RNNs were created.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  Feedforward Networks Recap
2.  Why They Work for Images
3.  Why They Fail for Sequences
4.  Lack of Memory
5.  Fixed-Length Input Problem
6.  Context Loss
7.  Temporal Dependencies
8.  Why RNNs Were Invented
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. Feedforward Networks Recap

``` text
Input → Hidden Layer → Output
```

Each prediction is independent.

------------------------------------------------------------------------

# 2. Why They Work for Images

Images are independent samples.

``` text
Image → CNN → Prediction
```

The model does not need previous images to classify the current one.

------------------------------------------------------------------------

# 3. Why They Fail for Sequences

"The dog chased the cat."

"The cat chased the dog."

The same words appear, but the order changes the meaning. Feedforward
networks do not naturally preserve this context.

------------------------------------------------------------------------

# 4. Lack of Memory

``` text
Word1 → Prediction

Word2 → Prediction

Word3 → Prediction
```

Each input is processed as if it were the first.

------------------------------------------------------------------------

# 5. Fixed-Length Input Problem

Dense networks expect a fixed number of inputs.

Real sequences vary:

-   3 words
-   20 words
-   500 words

------------------------------------------------------------------------

# 6. Context Loss

The word "bank" means different things in:

-   "The bank approved the loan."
-   "The boat reached the bank."

Previous words provide the context.

------------------------------------------------------------------------

# 7. Temporal Dependencies

Examples:

-   Speech recognition
-   Machine translation
-   Stock prices
-   Weather forecasting

Past observations influence future predictions.

------------------------------------------------------------------------

# 8. Why RNNs Were Invented

``` text
Input(t)
   │
Hidden State
   │
Output(t)
   │
Hidden State → Next Time Step
```

The hidden state gives the model memory.

------------------------------------------------------------------------

# 9. Python Example

``` python
sentence = "I love AI"
tokens = sentence.split()

for token in tokens:
    print(token)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Tokenize sentences.
2.  Compare predictions with and without previous context.
3.  Explain why remembering previous words matters.

------------------------------------------------------------------------

# 11. Interview Questions

### Why do feedforward networks fail for sequential data?

They have no memory and cannot model temporal dependencies.

### What problem motivated RNNs?

The need to preserve context across time steps.

### Give examples of sequential data.

-   Text
-   Speech
-   Time series

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Why feedforward networks struggle with sequences.
-   Memory limitations.
-   Context loss.
-   Temporal dependencies.
-   Motivation for RNNs.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 146 -- Recurrent Neural Networks (RNNs)**

You'll learn recurrent connections, hidden states, parameter sharing
across time steps, forward propagation through sequences, and the
mathematical foundations of RNNs.
