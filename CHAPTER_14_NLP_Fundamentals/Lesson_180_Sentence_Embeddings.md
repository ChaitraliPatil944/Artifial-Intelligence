# Chapter 14 -- NLP Fundamentals

# Lesson 180 -- Sentence Embeddings

> **Sentence Embeddings are dense vector representations of entire
> sentences or paragraphs. Unlike word embeddings that represent
> individual words, sentence embeddings capture the overall meaning of a
> complete sentence, making them essential for semantic search, document
> retrieval, clustering, recommendation systems, and Retrieval-Augmented
> Generation (RAG).**

------------------------------------------------------------------------

# Learning Objectives

-   Understand sentence embeddings.
-   Learn why word embeddings are not enough.
-   Compare sentence and word embeddings.
-   Study popular sentence embedding models.
-   Understand semantic similarity.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What are Sentence Embeddings?
2.  Why Word Embeddings Are Not Enough
3.  How Sentence Embeddings Work
4.  Popular Sentence Embedding Models
5.  Semantic Similarity
6.  Applications
7.  Sentence vs Word Embeddings
8.  Python Implementation
9.  Best Practices
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What are Sentence Embeddings?

A sentence embedding converts an entire sentence into one dense vector.

``` text
"I love Artificial Intelligence."

↓

[0.18, -0.42, 0.71, ...]
```

The vector captures the meaning of the complete sentence.

------------------------------------------------------------------------

# 2. Why Word Embeddings Are Not Enough

Word embeddings represent individual words.

``` text
"I love AI"

↓

I
love
AI
```

But many tasks require understanding the whole sentence.

Example:

``` text
"The movie was not good."

"The movie was good."
```

The word **not** changes the overall meaning. Sentence embeddings
capture this better than averaging isolated word vectors.

------------------------------------------------------------------------

# 3. How Sentence Embeddings Work

General pipeline:

``` text
Sentence
    │
Tokenizer
    │
Embedding Model
    │
Pooling
    │
Sentence Vector
```

Pooling methods include:

-   Mean pooling
-   Max pooling
-   CLS token pooling (Transformer-based models)

------------------------------------------------------------------------

# 4. Popular Sentence Embedding Models

## Universal Sentence Encoder (USE)

-   Developed by Google
-   Efficient for semantic similarity
-   Works well for transfer learning

## Sentence-BERT (SBERT)

-   Built on BERT
-   Optimized for sentence similarity
-   Faster than comparing BERT embeddings token by token

Other models:

-   MiniLM
-   E5
-   BGE
-   Instructor Embeddings

------------------------------------------------------------------------

# 5. Semantic Similarity

Sentence embeddings allow meaningful comparison.

Example:

``` text
Sentence A:
"I enjoy machine learning."

Sentence B:
"I like studying AI."
```

Although the words differ, the meanings are similar.

Similarity is commonly measured using **Cosine Similarity**.

``` text
1.0  → Very similar

0.0  → Unrelated

-1.0 → Opposite direction
```

------------------------------------------------------------------------

# 6. Applications

-   Semantic Search
-   Document Retrieval
-   Retrieval-Augmented Generation (RAG)
-   Duplicate Detection
-   Recommendation Systems
-   Question Answering
-   Text Clustering
-   Chatbots

------------------------------------------------------------------------

# 7. Sentence vs Word Embeddings

  Word Embeddings             Sentence Embeddings
  --------------------------- -------------------------------
  Represent one word          Represent a complete sentence
  Limited context             Captures overall meaning
  Word2Vec, GloVe, FastText   SBERT, USE, E5
  Good for word similarity    Good for semantic search

------------------------------------------------------------------------

# 8. Python Implementation

``` python
from sentence_transformers import SentenceTransformer

model = SentenceTransformer(
    "all-MiniLM-L6-v2"
)

sentences = [
    "I love AI.",
    "Artificial Intelligence is fascinating."
]

embeddings = model.encode(sentences)

print(embeddings.shape)
```

Cosine similarity:

``` python
from sentence_transformers import util

score = util.cos_sim(
    embeddings[0],
    embeddings[1]
)

print(score)
```

------------------------------------------------------------------------

# 9. Best Practices

-   Choose embeddings trained for your task.
-   Normalize vectors before similarity search when appropriate.
-   Store embeddings in a vector database for large-scale retrieval.
-   Recompute embeddings if documents change.

------------------------------------------------------------------------

# 10. Mini Project

1.  Encode 1,000 news headlines.
2.  Compute cosine similarity.
3.  Find duplicate headlines.
4.  Cluster similar news.
5.  Build a simple semantic search engine.

------------------------------------------------------------------------

# 11. Interview Questions

### What is a sentence embedding?

A dense vector that represents the meaning of an entire sentence.

### Why not average Word2Vec vectors?

Averaging often loses word order and richer contextual information.

### Name two sentence embedding models.

-   Sentence-BERT (SBERT)
-   Universal Sentence Encoder (USE)

### Where are sentence embeddings used?

Semantic search, RAG, recommendation systems, clustering, and duplicate
detection.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Sentence embeddings.
-   Why they outperform simple word-vector averaging.
-   Popular embedding models.
-   Semantic similarity.
-   Real-world applications.
-   Python implementation.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 181 -- Byte Pair Encoding (BPE)**

You'll learn how Byte Pair Encoding builds subword vocabularies, why
modern LLMs use subword tokenization, how BPE reduces out-of-vocabulary
words, and why it became one of the most influential tokenization
algorithms in NLP.
