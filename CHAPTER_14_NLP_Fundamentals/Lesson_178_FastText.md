# Chapter 14 -- NLP Fundamentals

# Lesson 178 -- FastText

> **FastText is a word embedding algorithm developed by Facebook AI
> Research (FAIR) that extends Word2Vec by representing each word as a
> collection of character n-grams. This allows it to generate meaningful
> embeddings for rare, misspelled, and even unseen words.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what FastText is.
-   Learn why FastText was developed.
-   Study character n-grams.
-   Compare FastText with Word2Vec.
-   Understand OOV handling.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is FastText?
2.  Why FastText?
3.  Character n-grams
4.  FastText Architecture
5.  OOV Words
6.  FastText vs Word2Vec
7.  Advantages & Limitations
8.  Python Implementation
9.  Mini Project
10. Interview Questions
11. Summary
12. What's Next?

------------------------------------------------------------------------

# 1. What is FastText?

FastText learns word embeddings using **subword information**.

``` text
running

↓

run + unn + nni + nin + ing
```

Instead of learning only one vector per word, it learns vectors for
character fragments.

------------------------------------------------------------------------

# 2. Why FastText?

Word2Vec struggles with:

-   Rare words
-   Misspellings
-   New words
-   Richly inflected languages

FastText addresses these issues using character n-grams.

------------------------------------------------------------------------

# 3. Character n-grams

Example:

``` text
apple
```

For n = 3:

``` text
<ap
app
ppl
ple
le>
```

(`<` and `>` represent word boundaries.)

The final embedding is computed from all n-gram vectors.

------------------------------------------------------------------------

# 4. FastText Architecture

``` text
Raw Word
    │
Character n-grams
    │
Embedding Lookup
    │
Average / Sum
    │
Final Word Embedding
```

Training objectives are similar to Word2Vec:

-   CBOW
-   Skip-Gram

------------------------------------------------------------------------

# 5. OOV (Out-of-Vocabulary) Words

Example:

``` text
chatgptification
```

Even if unseen during training, FastText can estimate its embedding
because it understands its character pieces.

This greatly reduces the OOV problem.

------------------------------------------------------------------------

# 6. FastText vs Word2Vec

  Word2Vec                    FastText
  --------------------------- ----------------------------------
  Learns whole-word vectors   Learns character n-grams
  Poor OOV handling           Excellent OOV handling
  Better for common words     Better for rare and unseen words
  Smaller model               Slightly larger model

------------------------------------------------------------------------

# 7. Advantages & Limitations

## Advantages

-   Handles misspellings
-   Learns morphology
-   Better for low-resource languages
-   Reduces OOV issues

## Limitations

-   Larger memory footprint
-   Slightly slower training
-   Still produces static embeddings

------------------------------------------------------------------------

# 8. Python Implementation

``` python
from gensim.models import FastText

sentences = [
    ["i","love","nlp"],
    ["fasttext","handles","rare","words"]
]

model = FastText(
    sentences,
    vector_size=100,
    window=5,
    min_count=1
)

print(model.wv["fasttext"])
```

------------------------------------------------------------------------

# 9. Mini Project

1.  Train Word2Vec and FastText on the same corpus.
2.  Introduce misspelled words.
3.  Compare nearest neighbors.
4.  Compare OOV performance.
5.  Visualize embeddings.

------------------------------------------------------------------------

# 10. Interview Questions

### What is FastText?

A word embedding algorithm that represents words using character
n-grams.

### Why is FastText better than Word2Vec for unseen words?

Because it builds embeddings from subword units instead of relying only
on complete words.

### What are character n-grams?

Small overlapping character sequences extracted from a word.

### Does FastText produce contextual embeddings?

No. Like Word2Vec, FastText produces static embeddings.

------------------------------------------------------------------------

# 11. Summary

You learned:

-   FastText fundamentals.
-   Character n-grams.
-   OOV handling.
-   FastText architecture.
-   Comparison with Word2Vec.
-   Python implementation.

------------------------------------------------------------------------

# 12. What's Next?

**Lesson 179 -- GloVe**

You'll learn how GloVe (Global Vectors for Word Representation) combines
global corpus statistics with local context to produce high-quality word
embeddings, and how it compares with Word2Vec and FastText.
