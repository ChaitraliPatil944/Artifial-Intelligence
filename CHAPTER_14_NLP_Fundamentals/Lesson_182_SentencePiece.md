# Chapter 14 -- NLP Fundamentals

# Lesson 182 -- SentencePiece

> **SentencePiece is a language-independent subword tokenization library
> developed by Google. Unlike traditional tokenizers that rely on
> whitespace, SentencePiece treats text as a raw sequence of Unicode
> characters, making it highly effective for multilingual NLP and modern
> Large Language Models (LLMs).**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what SentencePiece is.
-   Learn why it was developed.
-   Study BPE and Unigram modes.
-   Understand whitespace-independent tokenization.
-   Learn how SentencePiece builds vocabularies.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is SentencePiece?
2.  Why SentencePiece?
3.  How SentencePiece Works
4.  BPE vs Unigram Mode
5.  Vocabulary Training
6.  Special Tokens
7.  SentencePiece vs BPE
8.  Applications
9.  Python Implementation
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is SentencePiece?

SentencePiece converts raw text into subword tokens without requiring
spaces.

``` text
Raw Text
   │
SentencePiece
   │
Subword Tokens
```

It supports virtually any language represented in Unicode.

------------------------------------------------------------------------

# 2. Why SentencePiece?

Many languages do not separate words using spaces.

Examples:

-   Japanese
-   Chinese
-   Thai

SentencePiece works directly on raw text, avoiding language-specific
preprocessing.

Benefits:

-   Language independent
-   Consistent preprocessing
-   Excellent multilingual support

------------------------------------------------------------------------

# 3. How SentencePiece Works

Pipeline:

``` text
Raw Corpus
    │
Unicode Characters
    │
Train Vocabulary
    │
Learn Subwords
    │
Encode Text
```

Whitespace is treated as a normal symbol rather than a delimiter.

------------------------------------------------------------------------

# 4. BPE vs Unigram Mode

SentencePiece supports two training algorithms.

## BPE Mode

-   Repeatedly merges frequent symbol pairs.
-   Similar to Byte Pair Encoding.

## Unigram Language Model

-   Starts with a large vocabulary.
-   Removes less useful tokens iteratively.
-   Chooses the most probable tokenization.

  BPE               Unigram
  ----------------- ----------------------------
  Merge-based       Probability-based
  Deterministic     Probabilistic
  Faster training   More flexible segmentation

------------------------------------------------------------------------

# 5. Vocabulary Training

Example:

``` text
internationalization
```

Possible segmentation:

``` text
▁international
ization
```

or

``` text
▁inter
national
ization
```

The model learns the segmentation that best represents the training
corpus.

------------------------------------------------------------------------

# 6. Special Tokens

Common tokens include:

  Token     Purpose
  --------- -----------------------
  `<unk>`   Unknown token
  `<pad>`   Padding
  `<bos>`   Beginning of sequence
  `<eos>`   End of sequence

SentencePiece also uses:

``` text
▁
```

to represent whitespace.

------------------------------------------------------------------------

# 7. SentencePiece vs BPE

  BPE                                   SentencePiece
  ------------------------------------- --------------------------------
  Usually requires pre-tokenized text   Uses raw text
  Mostly whitespace-based               Whitespace independent
  Single algorithm                      Supports BPE and Unigram
  Good for many tasks                   Excellent for multilingual NLP

------------------------------------------------------------------------

# 8. Applications

SentencePiece is widely used in:

-   T5
-   ALBERT
-   LLaMA
-   mT5
-   MarianMT

It is especially useful for multilingual language models.

------------------------------------------------------------------------

# 9. Python Implementation

``` python
import sentencepiece as spm

spm.SentencePieceTrainer.train(
    input="corpus.txt",
    model_prefix="spm",
    vocab_size=8000
)

sp = spm.SentencePieceProcessor()
sp.load("spm.model")

tokens = sp.encode(
    "Natural Language Processing",
    out_type=str
)

print(tokens)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Train a SentencePiece tokenizer.
2.  Compare BPE and Unigram modes.
3.  Measure vocabulary size.
4.  Tokenize multilingual sentences.
5.  Compare results with a whitespace tokenizer.

------------------------------------------------------------------------

# 11. Interview Questions

### What is SentencePiece?

A language-independent subword tokenizer that operates directly on raw
Unicode text.

### Why doesn't SentencePiece require whitespace?

Because it treats whitespace as a normal symbol rather than a word
boundary.

### Which algorithms does SentencePiece support?

-   Byte Pair Encoding (BPE)
-   Unigram Language Model

### Why is SentencePiece popular?

It performs well across many languages and is widely used in modern
LLMs.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   SentencePiece fundamentals.
-   Whitespace-independent tokenization.
-   BPE and Unigram modes.
-   Vocabulary training.
-   Special tokens.
-   Python implementation.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 183 -- TF-IDF**

You'll learn how Term Frequency--Inverse Document Frequency (TF-IDF)
measures word importance, compare it with Bag of Words, understand
document vectors, and discover why TF-IDF remains a strong baseline for
many classical NLP tasks.
