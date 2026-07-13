# Chapter 14 -- NLP Fundamentals

# Lesson 176 -- Word Embeddings

> **Word Embeddings are dense numerical vector representations of words
> that capture semantic and syntactic relationships. Unlike one-hot
> encoding, embeddings place similar words close together in a
> continuous vector space, allowing machine learning models to
> understand relationships between words.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand word embeddings.
-   Learn why one-hot encoding is limited.
-   Compare sparse and dense representations.
-   Understand semantic similarity.
-   Learn embedding layers in deep learning.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What are Word Embeddings?
2.  Why One-Hot Encoding Fails
3.  Dense vs Sparse Vectors
4.  Semantic Meaning
5.  Embedding Space
6.  Cosine Similarity
7.  Embedding Layer
8.  Static vs Contextual Embeddings
9.  TensorFlow Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What are Word Embeddings?

Word embeddings represent each word as a dense vector of real numbers.

``` text
Dog

↓

[0.23, -0.71, 0.45, ...]
```

Words with similar meanings have similar vectors.

------------------------------------------------------------------------

# 2. Why One-Hot Encoding Fails

One-hot encoding:

``` text
Cat = [1,0,0,0]

Dog = [0,1,0,0]
```

Problems:

-   Extremely sparse
-   Large memory usage
-   No semantic relationship
-   Every word appears equally distant

------------------------------------------------------------------------

# 3. Dense vs Sparse Vectors

  Sparse (One-Hot)   Dense (Embedding)
  ------------------ ------------------------
  Mostly zeros       Real-valued numbers
  High dimensional   Low dimensional
  No meaning         Captures relationships
  Memory intensive   Efficient

------------------------------------------------------------------------

# 4. Semantic Meaning

Embeddings learn relationships automatically.

Examples:

``` text
King ≈ Queen

Doctor ≈ Hospital

Paris ≈ France
```

Words used in similar contexts become close together.

------------------------------------------------------------------------

# 5. Embedding Space

``` text
          Queen
            ●

 King ●

            Princess

 Dog ●

 Cat ●

      Car ●
```

Nearby words are semantically similar.

------------------------------------------------------------------------

# 6. Cosine Similarity

Cosine similarity measures how similar two vectors are.

Formula:

``` text
Cos(A,B) = (A · B) / (||A|| ||B||)
```

Values:

-   1 → Very similar
-   0 → Unrelated
-   -1 → Opposite direction

------------------------------------------------------------------------

# 7. Embedding Layer

Neural networks learn embeddings using an embedding layer.

``` text
Token IDs

↓

Embedding Layer

↓

Dense Vectors

↓

LSTM / Transformer
```

------------------------------------------------------------------------

# 8. Static vs Contextual Embeddings

  Static                      Contextual
  --------------------------- ------------------------------
  One vector per word         Depends on sentence context
  Word2Vec, GloVe, FastText   BERT, GPT
  Same meaning everywhere     Meaning changes with context

Example:

``` text
bank
```

Financial institution vs river bank receive different contextual
embeddings.

------------------------------------------------------------------------

# 9. TensorFlow Example

``` python
from tensorflow.keras.layers import Embedding

embedding = Embedding(
    input_dim=10000,
    output_dim=128
)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Tokenize a text dataset.
2.  Build an embedding layer.
3.  Train a sentiment classifier.
4.  Visualize embeddings with PCA or t-SNE.
5.  Find similar words using cosine similarity.

------------------------------------------------------------------------

# 11. Interview Questions

### What is a word embedding?

A dense vector representation of a word.

### Why are embeddings better than one-hot encoding?

They capture semantic relationships while using fewer dimensions.

### What does cosine similarity measure?

The similarity between two embedding vectors.

### Give examples of static embeddings.

Word2Vec, GloVe, FastText.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Word embeddings.
-   One-hot encoding limitations.
-   Dense vector representations.
-   Semantic similarity.
-   Embedding layers.
-   Static vs contextual embeddings.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 177 -- Word2Vec**

You'll learn how Word2Vec learns embeddings using CBOW and Skip-Gram
architectures, negative sampling, training objectives, and why it
revolutionized classical NLP.
