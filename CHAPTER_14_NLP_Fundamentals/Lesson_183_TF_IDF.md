# Chapter 14 -- NLP Fundamentals

# Lesson 183 -- TF-IDF (Term Frequency--Inverse Document Frequency)

> **TF-IDF (Term Frequency--Inverse Document Frequency) is a statistical
> technique used to measure how important a word is in a document
> relative to an entire collection of documents (corpus). It is one of
> the most influential feature extraction methods in classical Natural
> Language Processing and Information Retrieval.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand TF-IDF.
-   Learn Term Frequency (TF).
-   Learn Document Frequency (DF) and Inverse Document Frequency (IDF).
-   Compute TF-IDF scores.
-   Compare TF-IDF with Bag of Words.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is TF-IDF?
2.  Why TF-IDF?
3.  Term Frequency (TF)
4.  Document Frequency (DF)
5.  Inverse Document Frequency (IDF)
6.  TF-IDF Formula
7.  TF-IDF Matrix
8.  TF-IDF vs Bag of Words
9.  Applications
10. Python Implementation
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is TF-IDF?

TF-IDF measures the importance of a word in a document.

A word is important if:

-   It appears frequently in one document.
-   It appears rarely across other documents.

``` text
Corpus
   │
Compute TF
   │
Compute IDF
   │
Multiply
   │
TF-IDF Score
```

------------------------------------------------------------------------

# 2. Why TF-IDF?

Common words such as:

``` text
the
is
and
of
```

appear everywhere.

They carry little information.

TF-IDF assigns:

-   Lower scores to common words.
-   Higher scores to informative words.

------------------------------------------------------------------------

# 3. Term Frequency (TF)

Term Frequency measures how often a word appears in a document.

Formula:

``` text
TF = (Number of occurrences of a word)
/ (Total words in document)
```

Example:

Document:

``` text
AI is amazing.
AI changes the world.
```

Word:

``` text
AI
```

appears twice.

------------------------------------------------------------------------

# 4. Document Frequency (DF)

Document Frequency counts how many documents contain a word.

Example:

``` text
Corpus

Doc1 → AI

Doc2 → AI

Doc3 → ML
```

DF(AI) = 2

DF(ML) = 1

------------------------------------------------------------------------

# 5. Inverse Document Frequency (IDF)

IDF reduces the importance of very common words.

Formula:

``` text
IDF = log(
Total Documents
/
Documents containing the word
)
```

Interpretation:

-   High IDF → Rare, informative word.
-   Low IDF → Common word.

------------------------------------------------------------------------

# 6. TF-IDF Formula

``` text
TF-IDF = TF × IDF
```

Example:

  Word       TF   IDF   TF-IDF
  ------ ------ ----- --------
  AI       0.20   1.6     0.32
  the      0.10   0.1     0.01

The word **AI** receives a much higher importance score.

------------------------------------------------------------------------

# 7. TF-IDF Matrix

Example:

  Document       AI     ML   Data
  ---------- ------ ------ ------
  Doc1         0.65   0.00   0.20
  Doc2         0.10   0.70   0.15
  Doc3         0.40   0.25   0.60

Each document becomes a numerical feature vector.

------------------------------------------------------------------------

# 8. TF-IDF vs Bag of Words

  Bag of Words              TF-IDF
  ------------------------- -----------------------------------------
  Counts word occurrences   Weighs word importance
  Common words dominate     Common words down-weighted
  Simpler                   More informative
  Good baseline             Better for retrieval and classification

------------------------------------------------------------------------

# 9. Applications

-   Search Engines
-   Information Retrieval
-   Spam Detection
-   Document Classification
-   Document Clustering
-   Keyword Extraction
-   Recommendation Systems

------------------------------------------------------------------------

# 10. Python Implementation

``` python
from sklearn.feature_extraction.text import TfidfVectorizer

documents = [
    "I love AI",
    "AI changes the world",
    "Machine learning is amazing"
]

vectorizer = TfidfVectorizer()

X = vectorizer.fit_transform(documents)

print(vectorizer.get_feature_names_out())
print(X.toarray())
```

------------------------------------------------------------------------

# 11. Mini Project

1.  Collect 500 news articles.
2.  Compute TF-IDF vectors.
3.  Find the top keywords in each article.
4.  Train a text classifier.
5.  Compare TF-IDF with Bag of Words.

------------------------------------------------------------------------

# 12. Interview Questions

### What is TF-IDF?

A weighting technique that measures the importance of a word within a
document relative to a corpus.

### Why is IDF necessary?

To reduce the influence of very common words that provide little
information.

### Difference between TF and IDF?

TF measures frequency within one document, while IDF measures rarity
across all documents.

### Where is TF-IDF used?

Search engines, information retrieval, document classification,
clustering, and keyword extraction.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   TF
-   DF
-   IDF
-   TF-IDF formula
-   TF-IDF matrix
-   Comparison with Bag of Words
-   Applications
-   Python implementation

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 184 -- Comparative Study of Classical NLP Representations**

You'll compare Bag of Words, TF-IDF, Word2Vec, FastText, GloVe, Sentence
Embeddings, BPE, and SentencePiece, understand their strengths,
weaknesses, use cases, and build a decision framework for selecting the
right representation for different NLP tasks.
