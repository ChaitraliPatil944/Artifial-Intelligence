# Chapter 14 -- NLP Fundamentals

# Lesson 175 -- Tokenization

> **Tokenization is the process of breaking raw text into smaller units
> called tokens. These tokens may be words, subwords, characters, or
> even sentences. Tokenization is the first major step after text
> cleaning and forms the foundation of every NLP pipeline, from
> classical machine learning to modern Large Language Models (LLMs).**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what tokenization is.
-   Learn why tokenization is necessary.
-   Study different types of tokenization.
-   Understand vocabularies, token IDs, and OOV words.
-   Explore tokenization in modern LLMs.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Tokenization?
2.  Why Tokenization is Needed
3.  Types of Tokenization
4.  Vocabulary Creation
5.  Token IDs & OOV Tokens
6.  Padding & Truncation
7.  Tokenization in Modern LLMs
8.  Python Implementation
9.  Best Practices
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is Tokenization?

Tokenization converts text into smaller pieces called **tokens**.

Example:

``` text
"I love Artificial Intelligence."
```

Word tokens:

``` text
["I", "love", "Artificial", "Intelligence"]
```

These tokens are later converted into numbers that a model can process.

------------------------------------------------------------------------

# 2. Why Tokenization is Needed

Computers cannot directly understand raw text.

Pipeline:

``` text
Raw Text
   │
Tokenization
   │
Tokens
   │
Token IDs
   │
Neural Network
```

Benefits:

-   Makes text machine-readable.
-   Standardizes input.
-   Builds vocabularies.
-   Enables embeddings.

------------------------------------------------------------------------

# 3. Types of Tokenization

## Word Tokenization

``` text
"I love AI"

↓

["I", "love", "AI"]
```

Advantages:

-   Easy to understand
-   Good for classical NLP

Disadvantages:

-   Large vocabulary
-   Cannot handle unknown words well

------------------------------------------------------------------------

## Sentence Tokenization

``` text
Hello World. NLP is fun!

↓

["Hello World.", "NLP is fun!"]
```

Used in:

-   Document summarization
-   Paragraph analysis

------------------------------------------------------------------------

## Character Tokenization

``` text
AI

↓

["A", "I"]
```

Advantages:

-   Handles unseen words

Disadvantages:

-   Longer sequences
-   Slower training

------------------------------------------------------------------------

## Subword Tokenization (Introduction)

``` text
unbelievable

↓

["un", "believ", "able"]
```

This balances vocabulary size and flexibility and is widely used in
LLMs.

------------------------------------------------------------------------

# 4. Vocabulary Creation

A vocabulary maps unique tokens to unique IDs.

Example:

  Token     ID
  ------- ----
  I          1
  love       2
  AI         3
  NLP        4

Sentence:

``` text
I love AI
```

becomes

``` text
[1, 2, 3]
```

------------------------------------------------------------------------

# 5. Token IDs & OOV Tokens

### Token IDs

Models process integers, not words.

``` text
"cat"

↓

125
```

### OOV (Out-of-Vocabulary) Token

Unknown words are mapped to a special token.

``` text
<UNK>
```

Example:

``` text
QuantumGPT

↓

<UNK>
```

Modern subword tokenizers greatly reduce OOV problems.

------------------------------------------------------------------------

# 6. Padding & Truncation

Neural networks expect batches of equal-length sequences.

Example:

``` text
["I", "love", "AI"]

↓

[I, love, AI, PAD, PAD]
```

Long sequences may be truncated:

``` text
Maximum Length = 5
```

------------------------------------------------------------------------

# 7. Tokenization in Modern LLMs

Modern models rarely use word-level tokenization.

Instead they use:

-   Byte Pair Encoding (BPE)
-   SentencePiece
-   WordPiece
-   Unigram Language Model

These methods split rare words into meaningful subwords.

Example:

``` text
internationalization

↓

["international", "ization"]
```

or

``` text
["inter", "national", "ization"]
```

depending on the tokenizer.

------------------------------------------------------------------------

# 8. Python Implementation

## Word Tokenization (NLTK)

``` python
from nltk.tokenize import word_tokenize

text = "Natural Language Processing is amazing!"

tokens = word_tokenize(text)

print(tokens)
```

## Hugging Face Tokenizer

``` python
from transformers import AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("bert-base-uncased")

tokens = tokenizer.tokenize("I love Artificial Intelligence")

print(tokens)
```

------------------------------------------------------------------------

# 9. Best Practices

-   Choose the tokenizer based on the model.
-   Keep preprocessing consistent during training and inference.
-   Use subword tokenizers for modern NLP models.
-   Avoid building unnecessarily large vocabularies.

------------------------------------------------------------------------

# 10. Mini Project

1.  Load a text dataset.
2.  Perform word tokenization.
3.  Build a vocabulary.
4.  Convert tokens into IDs.
5.  Pad sequences to equal length.
6.  Compare word and subword tokenization.

------------------------------------------------------------------------

# 11. Interview Questions

### What is tokenization?

The process of splitting text into smaller units called tokens.

### Why is tokenization important?

It converts text into a representation suitable for machine learning
models.

### What is an OOV token?

A special token used for words not present in the vocabulary.

### Why do LLMs prefer subword tokenization?

It reduces vocabulary size while handling unseen words efficiently.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   What tokenization is.
-   Different tokenization methods.
-   Vocabulary creation.
-   Token IDs.
-   OOV tokens.
-   Padding and truncation.
-   Tokenization in modern LLMs.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 176 -- Word Embeddings**

You'll learn how words are converted into dense numerical vectors, why
embeddings are better than one-hot encoding, how semantic relationships
are captured, and how embeddings became one of the biggest breakthroughs
in NLP.
