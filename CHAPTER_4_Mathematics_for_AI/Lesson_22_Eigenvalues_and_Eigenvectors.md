# Lesson 22: Eigenvalues & Eigenvectors

## Part III -- Mathematics for AI

> **Goal:** Understand eigenvalues and eigenvectors intuitively, learn
> why they were invented, and discover how they are used in AI, Machine
> Learning, and Data Science.

------------------------------------------------------------------------

# Estimated Reading Time

75--90 Minutes

# Difficulty

⭐⭐⭐⭐⭐

# Prerequisites

-   Lessons 13--21

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson you will be able to:

-   Explain eigenvalues and eigenvectors intuitively.
-   Understand why they were invented.
-   Interpret them geometrically.
-   Calculate simple eigenvalues and eigenvectors.
-   Explain their role in PCA, Computer Vision, and AI.

------------------------------------------------------------------------

# 1. Why Were Eigenvalues & Eigenvectors Invented?

Imagine you stretch a rubber sheet.

Most arrows drawn on it change both:

-   Length
-   Direction

But a few special arrows only change **length**.

They continue pointing in the same direction.

Mathematicians wanted to identify these special directions.

Those directions are called **eigenvectors**.

The amount of stretching is called the **eigenvalue**.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine standing on a moving walkway.

``` text
➡ Walk with the walkway

You move faster.

Direction stays the same.
```

Now walk sideways.

``` text
➡ Walk across the walkway

Your direction changes.
```

Only one direction remained unchanged.

That is the idea behind an eigenvector.

------------------------------------------------------------------------

# 3. Definition

An **eigenvector** is a non-zero vector whose direction remains
unchanged after a linear transformation.

An **eigenvalue** tells us how much that vector is stretched or
compressed.

The famous equation is:

``` text
A x = λ x
```

Where:

-   A = Transformation Matrix
-   x = Eigenvector
-   λ (lambda) = Eigenvalue

------------------------------------------------------------------------

# 4. Visual Intuition

Before transformation:

``` text
      ↑
      │
      ●
```

After transformation:

``` text
         ↑
         │
         ●
```

Same direction.

Different length.

------------------------------------------------------------------------

# 5. Stretching and Compression

``` text
Eigenvalue > 1

Stretch

────────▶

Eigenvalue = 1

No change

Eigenvalue < 1

Compression
```

------------------------------------------------------------------------

# 6. Negative Eigenvalues

A negative eigenvalue reverses direction.

``` text
Before

────▶

After

◀────
```

------------------------------------------------------------------------

# 7. Why AI Cares

Large datasets contain many correlated features.

Example:

``` text
Height

Weight

Age

Income

...
```

Not every direction in the data is equally important.

Eigenvectors help identify the important directions.

------------------------------------------------------------------------

# 8. Principal Component Analysis (PCA)

``` text
High-Dimensional Data
          │
          ▼
Covariance Matrix
          │
          ▼
Eigenvectors
          │
          ▼
Principal Components
          │
          ▼
Reduced Dimensions
```

PCA keeps the directions with the most information.

------------------------------------------------------------------------

# 9. Computer Vision

``` text
Face Images
      │
      ▼
Eigenfaces
      │
      ▼
Face Recognition
```

Face recognition systems historically used eigenvectors to find the most
informative facial patterns.

------------------------------------------------------------------------

# 10. Recommendation Systems

``` text
Large User Data
        │
        ▼
Find Important Patterns
        │
        ▼
Reduce Complexity
```

Eigenvectors help discover hidden structure.

------------------------------------------------------------------------

# 11. Neural Networks

Deep learning mainly relies on matrix operations, but eigenvalues are
useful for understanding:

-   Stability
-   Optimization
-   Training dynamics

------------------------------------------------------------------------

# 12. Worked Example

Matrix:

``` text
A =

[2 0
 0 3]
```

Eigenvectors:

``` text
(1,0)

(0,1)
```

Eigenvalues:

``` text
2

3
```

The x-axis stretches by 2.

The y-axis stretches by 3.

------------------------------------------------------------------------

# 13. Python Example

``` python
import numpy as np

A = np.array([[2,0],
              [0,3]])

values, vectors = np.linalg.eig(A)

print(values)
print(vectors)
```

------------------------------------------------------------------------

# 14. Common Mistakes

❌ Thinking every vector is an eigenvector.

❌ Confusing eigenvalues with eigenvectors.

❌ Believing eigenvectors always point in different directions.

------------------------------------------------------------------------

# 15. Interview Questions

### Basic

What is an eigenvector?

A vector whose direction remains unchanged after a linear
transformation.

### Intermediate

What does an eigenvalue represent?

It tells how much the corresponding eigenvector is stretched or
compressed.

### Advanced

Why are eigenvalues important in Machine Learning?

They help identify important directions in data, making techniques such
as PCA possible.

------------------------------------------------------------------------

# 16. Quick Revision

``` text
Matrix
   │
   ▼
Transformation
   │
   ▼
Eigenvectors
   │
   ▼
Eigenvalues
   │
   ▼
PCA
   │
   ▼
Dimensionality Reduction
```

------------------------------------------------------------------------

# Lesson Summary

-   Eigenvectors are special directions that remain unchanged during a
    transformation.
-   Eigenvalues measure how much those directions are stretched or
    compressed.
-   PCA uses eigenvectors to reduce dimensions while preserving useful
    information.
-   Eigenvalues and eigenvectors are important tools for understanding
    data structure and linear transformations.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 23

Singular Value Decomposition (SVD)

↓

Breaking Large Matrices into Simpler Parts
```
