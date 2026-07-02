# Lesson 23: Singular Value Decomposition (SVD)

## Part III -- Mathematics for AI

> **Goal:** Understand what Singular Value Decomposition (SVD) is, why
> it was invented, and how it powers recommendation systems, search
> engines, image compression, and Machine Learning.

------------------------------------------------------------------------

# Estimated Reading Time

75--90 Minutes

# Difficulty

⭐⭐⭐⭐⭐

# Prerequisites

-   Lessons 13--22

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson you will be able to:

-   Explain the intuition behind SVD.
-   Understand why SVD decomposes a matrix.
-   Interpret the matrices U, Σ and Vᵀ.
-   Connect SVD to PCA, recommendation systems and NLP.
-   Apply SVD using NumPy.

------------------------------------------------------------------------

# 1. Why Was SVD Invented?

Imagine a giant book containing millions of numbers.

``` text
Huge Matrix
```

Working directly with it is expensive.

Mathematicians asked:

> Can we break one complicated matrix into smaller, easier pieces?

SVD answers **yes**.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine a LEGO castle.

``` text
Castle
   │
   ▼
Take Apart
   │
   ▼
Bricks
```

Instead of studying the entire castle, you study the individual bricks.

SVD does the same thing for matrices.

------------------------------------------------------------------------

# 3. Definition

Singular Value Decomposition breaks any matrix **A** into three
matrices:

``` text
A = U Σ Vᵀ
```

Where:

-   **U** → Left singular vectors
-   **Σ** → Singular values
-   **Vᵀ** → Right singular vectors

------------------------------------------------------------------------

# 4. Visual Intuition

``` text
Large Matrix
      │
      ▼
+----------------+
|      A         |
+----------------+
      │
      ▼
Break Apart
      │
      ▼
U     Σ     Vᵀ
```

Instead of one difficult object, we get three easier ones.

------------------------------------------------------------------------

# 5. What Does Each Matrix Mean?

``` text
A = U Σ Vᵀ
```

### U

Represents important output directions.

### Σ (Sigma)

Contains the importance of each direction.

Larger values mean more important information.

### Vᵀ

Represents important input directions.

------------------------------------------------------------------------

# 6. Why Is SVD Useful?

Suppose this matrix contains movie ratings.

``` text
Users × Movies
```

Many entries are similar.

SVD discovers hidden patterns and compresses the information.

------------------------------------------------------------------------

# 7. Image Compression

``` text
Image
   │
   ▼
Pixel Matrix
   │
   ▼
SVD
   │
   ▼
Keep Largest Singular Values
   │
   ▼
Smaller Image
```

Small singular values often represent less important details.

------------------------------------------------------------------------

# 8. Recommendation Systems

``` text
Users × Movies
        │
        ▼
SVD
        │
        ▼
Hidden Preferences
        │
        ▼
Recommendations
```

Classic recommender systems use matrix factorization based on SVD ideas.

------------------------------------------------------------------------

# 9. Search Engines & NLP

``` text
Documents
      │
      ▼
Term-Document Matrix
      │
      ▼
SVD
      │
      ▼
Latent Topics
```

This idea appears in **Latent Semantic Analysis (LSA)**.

------------------------------------------------------------------------

# 10. Relationship with PCA

``` text
Dataset
    │
    ▼
SVD
    │
    ▼
Principal Components
```

Many PCA implementations compute principal components using SVD because
it is numerically stable.

------------------------------------------------------------------------

# 11. AI Applications

-   Image compression
-   Noise reduction
-   Recommendation systems
-   Topic modelling
-   Semantic search
-   Feature extraction
-   Data compression

------------------------------------------------------------------------

# 12. Python Example

``` python
import numpy as np

A = np.array([
    [1,2],
    [3,4],
    [5,6]
])

U, S, VT = np.linalg.svd(A)

print(U)
print(S)
print(VT)
```

------------------------------------------------------------------------

# 13. Common Mistakes

❌ Thinking SVD works only for square matrices.

❌ Confusing singular values with eigenvalues.

❌ Keeping every singular value when compression is desired.

------------------------------------------------------------------------

# 14. Interview Questions

### Basic

What is SVD?

A matrix decomposition technique that factors a matrix into U, Σ and Vᵀ.

### Intermediate

Why is SVD useful?

It compresses data, removes noise and reveals hidden structure.

### Advanced

Why do many PCA implementations use SVD?

Because SVD is efficient and numerically stable for computing principal
components.

------------------------------------------------------------------------

# 15. Quick Revision

``` text
Matrix
   │
   ▼
SVD
   │
   ├── U
   ├── Σ
   └── Vᵀ
        │
        ▼
Compression
Recommendation
PCA
Search
```

------------------------------------------------------------------------

# Lesson Summary

-   SVD decomposes one matrix into three simpler matrices.
-   Singular values measure the importance of information.
-   SVD powers recommendation systems, PCA, image compression and
    semantic search.
-   Modern AI libraries provide highly optimized implementations of SVD.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 24

Probability

↓

Understanding Uncertainty in Artificial Intelligence
```
