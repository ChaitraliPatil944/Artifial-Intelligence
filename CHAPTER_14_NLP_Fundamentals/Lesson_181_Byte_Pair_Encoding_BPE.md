# Chapter 14 -- NLP Fundamentals

# Lesson 181 -- Byte Pair Encoding (BPE)

> **Byte Pair Encoding (BPE) is a subword tokenization algorithm that
> builds a vocabulary by repeatedly merging the most frequent pairs of
> symbols. Originally developed for data compression, BPE became one of
> the most influential tokenization techniques in NLP because it reduces
> vocabulary size while handling rare and unseen words effectively.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what BPE is.
-   Learn why BPE was adopted in NLP.
-   Study the BPE merge algorithm.
-   Understand subword vocabularies.
-   Compare BPE with word and character tokenization.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is BPE?
2.  Why BPE?
3.  How BPE Works
4.  Step-by-Step Example
5.  Building the Vocabulary
6.  Advantages & Limitations
7.  BPE vs Other Tokenizers
8.  BPE in Modern LLMs
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is BPE?

BPE starts with individual characters and repeatedly merges the most
frequent adjacent pair.

``` text
l o w e r

↓

lo w er

↓

low er

↓

lower
```

The learned merges become the tokenizer vocabulary.

------------------------------------------------------------------------

# 2. Why BPE?

Word-level vocabularies become huge.

Character-level tokenization creates very long sequences.

BPE provides a balance.

``` text
Words
   │
Too Large
   │
BPE
   │
Compact Vocabulary
```

------------------------------------------------------------------------

# 3. How BPE Works

Pipeline:

``` text
Corpus
  │
Split into Characters
  │
Count Adjacent Pairs
  │
Merge Most Frequent Pair
  │
Repeat
  │
Final Subword Vocabulary
```

------------------------------------------------------------------------

# 4. Step-by-Step Example

Corpus:

``` text
low
lower
lowest
```

Initial symbols:

``` text
l o w
l o w e r
l o w e s t
```

Frequent pair:

``` text
l + o

↓

lo
```

Next:

``` text
lo + w

↓

low
```

Eventually the vocabulary contains useful pieces such as:

``` text
low
er
est
```

These pieces can form many words.

------------------------------------------------------------------------

# 5. Building the Vocabulary

Example vocabulary:

  Token     ID
  ------- ----
  low        1
  er         2
  est        3
  ing        4

Unknown words are decomposed into known subwords.

``` text
lowering

↓

low + er + ing
```

------------------------------------------------------------------------

# 6. Advantages & Limitations

## Advantages

-   Smaller vocabulary
-   Fewer OOV words
-   Efficient storage
-   Handles new words well

## Limitations

-   Merge rules depend on training corpus
-   Subwords are not always linguistically meaningful
-   Still static compared with contextual understanding

------------------------------------------------------------------------

# 7. BPE vs Other Tokenizers

  Method      Vocabulary   OOV    Sequence Length
  ----------- ------------ ------ -----------------
  Word        Very large   High   Short
  Character   Very small   None   Very long
  BPE         Moderate     Low    Moderate

------------------------------------------------------------------------

# 8. BPE in Modern LLMs

BPE is widely used in:

-   GPT family
-   RoBERTa
-   Many open-source LLMs

Example:

``` text
unbelievably

↓

un + believable + ly
```

The model already knows these subwords even if it has never seen the
complete word.

------------------------------------------------------------------------

# 9. Python Example

``` python
from tokenizers import Tokenizer
from tokenizers.models import BPE

tokenizer = Tokenizer(BPE())
```

Many libraries such as Hugging Face automatically train and apply BPE
tokenizers.

------------------------------------------------------------------------

# 10. Mini Project

1.  Train a BPE tokenizer.
2.  Compare it with word tokenization.
3.  Measure vocabulary size.
4.  Test unseen words.
5.  Compare sequence lengths.

------------------------------------------------------------------------

# 11. Interview Questions

### What is Byte Pair Encoding?

A subword tokenization algorithm that repeatedly merges frequent symbol
pairs.

### Why is BPE better than word tokenization?

It reduces vocabulary size while handling unseen words.

### Why is BPE better than character tokenization?

It produces shorter sequences while preserving flexibility.

### Where is BPE used?

GPT models and many modern NLP systems.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   BPE fundamentals.
-   Merge operations.
-   Subword vocabularies.
-   Advantages and limitations.
-   Applications in LLMs.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 182 -- SentencePiece**

You'll learn how SentencePiece tokenizes text without relying on
whitespace, supports multilingual NLP, and powers models such as T5,
ALBERT, and LLaMA.
