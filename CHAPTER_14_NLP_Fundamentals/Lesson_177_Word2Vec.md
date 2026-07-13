# Chapter 14 -- NLP Fundamentals

# Lesson 177 -- Word2Vec

> **Word2Vec is a neural-network-based algorithm introduced by Google in
> 2013 that learns dense vector representations of words by analyzing
> their surrounding context. It revolutionized NLP by showing that
> semantic relationships can be learned directly from large text
> corpora.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what Word2Vec is.
-   Learn why it was invented.
-   Study CBOW and Skip-Gram.
-   Understand context windows.
-   Learn Negative Sampling and Hierarchical Softmax.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Word2Vec?
2.  Why Word2Vec?
3.  Distributional Hypothesis
4.  CBOW
5.  Skip-Gram
6.  Context Window
7.  Negative Sampling
8.  Hierarchical Softmax
9.  Advantages & Limitations
10. Python Example
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is Word2Vec?

Word2Vec learns word embeddings by predicting relationships between
words.

``` text
"The cat sits on the mat"

↓

Learn vector representations
```

Similar words end up close together in vector space.

------------------------------------------------------------------------

# 2. Why Word2Vec?

Before Word2Vec:

-   One-Hot Encoding
-   Sparse vectors
-   No semantic understanding

After Word2Vec:

-   Dense vectors
-   Semantic similarity
-   Better NLP performance

------------------------------------------------------------------------

# 3. Distributional Hypothesis

> **Words appearing in similar contexts tend to have similar meanings.**

Example:

``` text
The cat drinks milk.
The dog drinks milk.
```

The model learns that **cat** and **dog** are related.

------------------------------------------------------------------------

# 4. Continuous Bag of Words (CBOW)

CBOW predicts the **center word** from surrounding context.

``` text
I love ___ intelligence

↓

artificial
```

``` text
Context Words
      │
      ▼
   Neural Network
      │
      ▼
 Target Word
```

### Advantages

-   Faster training
-   Works well on frequent words

------------------------------------------------------------------------

# 5. Skip-Gram

Skip-Gram predicts **surrounding words** from the center word.

``` text
artificial

↓

love, intelligence
```

``` text
Center Word
      │
      ▼
   Neural Network
      │
      ▼
Context Words
```

### Advantages

-   Better for rare words
-   Higher-quality embeddings

------------------------------------------------------------------------

# 6. Context Window

The context window defines how many neighboring words are considered.

Example:

``` text
I love artificial intelligence today
```

Window size = 2

Context for **artificial**:

``` text
love
artificial
intelligence
```

Larger windows capture broader semantics.

------------------------------------------------------------------------

# 7. Negative Sampling

Computing probabilities for every word is expensive.

Negative Sampling simplifies training.

``` text
Positive Pair

cat → milk

Negative Pair

cat → airplane
```

The model learns to distinguish real context from random words.

Benefits:

-   Faster training
-   Lower computational cost
-   Scales to large vocabularies

------------------------------------------------------------------------

# 8. Hierarchical Softmax

Instead of evaluating every word in the vocabulary:

``` text
Vocabulary

↓

Binary Tree

↓

Logarithmic Search
```

Useful for very large vocabularies.

------------------------------------------------------------------------

# 9. Advantages & Limitations

  -----------------------------------------------------------------------
  Advantages                         Limitations
  ---------------------------------- ------------------------------------
  Learns semantic relationships      Static embeddings

  Efficient                          One vector per word

  Works well on large corpora        Cannot model context changes

  Improves downstream NLP tasks      Replaced by contextual embeddings in
                                     modern LLMs
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 10. Python Example

``` python
from gensim.models import Word2Vec

sentences = [
    ["i", "love", "ai"],
    ["ai", "is", "powerful"],
    ["machine", "learning", "is", "fun"]
]

model = Word2Vec(
    sentences,
    vector_size=100,
    window=5,
    min_count=1,
    sg=1
)

print(model.wv["ai"])
```

`sg=0` → CBOW

`sg=1` → Skip-Gram

------------------------------------------------------------------------

# 11. Mini Project

1.  Download a text corpus.
2.  Train both CBOW and Skip-Gram models.
3.  Compare training time.
4.  Find similar words.
5.  Visualize embeddings using PCA or t-SNE.

------------------------------------------------------------------------

# 12. Interview Questions

### What is Word2Vec?

A neural algorithm that learns dense word embeddings from context.

### Difference between CBOW and Skip-Gram?

CBOW predicts the center word from context, while Skip-Gram predicts
surrounding words from the center word.

### Why is Negative Sampling used?

To reduce computational cost during training.

### What is the biggest limitation of Word2Vec?

It produces static embeddings, so a word has only one vector regardless
of context.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   Word2Vec fundamentals.
-   Distributional hypothesis.
-   CBOW.
-   Skip-Gram.
-   Context windows.
-   Negative Sampling.
-   Hierarchical Softmax.
-   Python implementation.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 178 -- FastText**

You'll learn how FastText improves upon Word2Vec by representing words
as collections of character n-grams, making it much better at handling
rare words, misspellings, and morphologically rich languages.
