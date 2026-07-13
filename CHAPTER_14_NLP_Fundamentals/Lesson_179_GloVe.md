# Chapter 14 -- NLP Fundamentals

# Lesson 179 -- GloVe (Global Vectors for Word Representation)

> **GloVe is a word embedding algorithm developed at Stanford University
> that learns word representations using global word co-occurrence
> statistics. Unlike Word2Vec, which predicts neighboring words, GloVe
> combines local context with global corpus information to produce rich
> semantic embeddings.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what GloVe is.
-   Learn why GloVe was developed.
-   Understand the co-occurrence matrix.
-   Learn how GloVe differs from Word2Vec and FastText.
-   Use pretrained GloVe embeddings.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is GloVe?
2.  Why GloVe?
3.  Global Co-occurrence Matrix
4.  Training Intuition
5.  Local vs Global Information
6.  GloVe vs Word2Vec vs FastText
7.  Advantages & Limitations
8.  Python Example
9.  Mini Project
10. Interview Questions
11. Summary
12. What's Next?

------------------------------------------------------------------------

# 1. What is GloVe?

GloVe stands for **Global Vectors for Word Representation**.

It learns embeddings by analyzing how frequently words appear together
throughout an entire corpus.

``` text
Large Text Corpus
      │
Word Co-occurrence Statistics
      │
Dense Word Embeddings
```

------------------------------------------------------------------------

# 2. Why GloVe?

Word2Vec mainly learns from local context.

GloVe additionally uses **global statistics**.

Example:

``` text
ice  → cold, snow, winter

steam → hot, water
```

Word relationships become clearer when considering the entire corpus.

------------------------------------------------------------------------

# 3. Global Co-occurrence Matrix

A co-occurrence matrix counts how often two words appear together.

Example:

  Word      king   queen   crown
  ------- ------ ------- -------
  king        20      18      25
  queen       18      21      19
  crown       25      19      15

Words that frequently appear together are likely to be semantically
related.

------------------------------------------------------------------------

# 4. Training Intuition

Pipeline:

``` text
Corpus
   │
Co-occurrence Matrix
   │
Optimization
   │
Embedding Vectors
```

The model learns vectors whose relationships explain observed
co-occurrence counts.

------------------------------------------------------------------------

# 5. Local vs Global Information

  Local Context               Global Statistics
  --------------------------- ------------------------------
  Nearby words                Entire corpus
  Word2Vec                    GloVe
  Short-range relationships   Broad semantic relationships

GloVe combines both ideas during training.

------------------------------------------------------------------------

# 6. GloVe vs Word2Vec vs FastText

  Feature                  Word2Vec   FastText   GloVe
  ------------------------ ---------- ---------- -------
  Uses local context       ✅         ✅         ✅
  Uses global statistics   ❌         ❌         ✅
  Character n-grams        ❌         ✅         ❌
  Handles OOV well         ❌         ✅         ❌
  Static embeddings        ✅         ✅         ✅

------------------------------------------------------------------------

# 7. Advantages & Limitations

## Advantages

-   Captures semantic relationships well
-   Uses global corpus knowledge
-   Widely available pretrained vectors
-   Strong performance on classical NLP tasks

## Limitations

-   Static embeddings
-   Cannot distinguish word meaning by context
-   Requires co-occurrence statistics before training

------------------------------------------------------------------------

# 8. Python Example

``` python
import gensim.downloader as api

glove = api.load("glove-wiki-gigaword-100")

print(glove["king"][:10])

print(glove.most_similar("queen"))
```

------------------------------------------------------------------------

# 9. Mini Project

1.  Download pretrained GloVe vectors.
2.  Load them into Python.
3.  Find similar words.
4.  Compare results with Word2Vec.
5.  Visualize embeddings using PCA or t-SNE.

------------------------------------------------------------------------

# 10. Interview Questions

### What does GloVe stand for?

Global Vectors for Word Representation.

### How is GloVe different from Word2Vec?

GloVe learns from global co-occurrence statistics, while Word2Vec
primarily learns by predicting nearby words.

### Does GloVe produce contextual embeddings?

No. Each word has one fixed embedding.

### What is the biggest limitation of GloVe?

It cannot represent different meanings of the same word in different
contexts.

------------------------------------------------------------------------

# 11. Summary

You learned:

-   GloVe fundamentals.
-   Co-occurrence matrices.
-   Global vs local learning.
-   Comparison with Word2Vec and FastText.
-   Python implementation.

------------------------------------------------------------------------

# 12. What's Next?

**Lesson 180 -- Sentence Embeddings**

You'll learn how entire sentences and paragraphs are converted into
dense vectors, why sentence embeddings are different from word
embeddings, and how they power semantic search, retrieval systems,
clustering, and modern Retrieval-Augmented Generation (RAG).
