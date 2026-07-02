# Lesson 20: Basis & Dimension

## Part III -- Mathematics for AI

> **Goal:** Understand the ideas of basis and dimension, why they
> matter, and how they help AI represent complex information
> efficiently.

------------------------------------------------------------------------

# Estimated Reading Time

60--75 Minutes

# Difficulty

⭐⭐⭐⭐☆

# Prerequisites

-   Lesson 13 -- Basic Mathematics Refresher
-   Lesson 14 -- Linear Algebra
-   Lesson 15 -- Vectors
-   Lesson 16 -- Matrices
-   Lesson 17 -- Matrix Operations
-   Lesson 18 -- Systems of Linear Equations
-   Lesson 19 -- Vector Spaces

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson you will be able to:

-   Explain basis and dimension.
-   Understand linear independence.
-   Differentiate basis from dimension.
-   Explain why dimensionality matters in AI.
-   Connect these ideas to embeddings and PCA.

------------------------------------------------------------------------

# 1. Why Were Basis and Dimension Invented?

Imagine building every LEGO model using only a few types of blocks.

``` text
Few Basic Blocks
       │
       ▼
Thousands of Models
```

Mathematicians asked a similar question:

> "What is the smallest set of vectors needed to build every other
> vector?"

The answer is called a **basis**.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine painting.

``` text
Red
Blue
Yellow
```

Using just these primary colors, you can create many other colors.

Those primary colors act like a basis.

------------------------------------------------------------------------

# 3. What is a Basis?

A **basis** is the smallest set of vectors that can generate every
vector in a vector space.

Example in 2D:

``` text
e₁ = (1,0)
e₂ = (0,1)
```

Using these two vectors you can reach any point on the 2D plane.

------------------------------------------------------------------------

# 4. Linear Independence

A basis must contain **independent** vectors.

Bad example:

``` text
(1,0)

(2,0)
```

The second vector is just a scaled version of the first.

It adds no new information.

Good example:

``` text
(1,0)

(0,1)
```

These are independent.

------------------------------------------------------------------------

# 5. What is Dimension?

The **dimension** of a vector space is the number of vectors in its
basis.

Examples:

``` text
Line     → 1 Dimension

Plane    → 2 Dimensions

Space    → 3 Dimensions
```

------------------------------------------------------------------------

# 6. Visual Intuition

``` text
1D

------------>

2D

     ^
     |
     |
-----+------>

3D

      z
      ^
     /
    /
   O-----> y
  /
 x
```

Higher dimensions follow the same mathematical rules.

------------------------------------------------------------------------

# 7. Basis in AI

Suppose a customer is described by:

``` text
Age
Income
Height
Weight
```

Feature Vector

``` text
[22, 50000, 170, 60]
```

Each feature contributes one dimension.

------------------------------------------------------------------------

# 8. Why Dimension Matters

More dimensions can describe more information.

But they also increase:

-   Memory usage
-   Computation time
-   Model complexity

This is why AI often reduces dimensions.

------------------------------------------------------------------------

# 9. Dimensionality Reduction

``` text
100 Features
      │
      ▼
PCA
      │
      ▼
10 Features
```

The goal is to keep important information while removing redundancy.

------------------------------------------------------------------------

# 10. Embeddings

A sentence becomes:

``` text
768 Numbers
```

Instead of thousands of words.

Embeddings compress meaning into a manageable number of dimensions.

------------------------------------------------------------------------

# 11. Neural Networks

``` text
Input Space
      │
      ▼
Hidden Representation
      │
      ▼
Output Space
```

Neural networks continuously transform data into new feature spaces.

------------------------------------------------------------------------

# 12. Python Example

``` python
import numpy as np

v1 = np.array([1,0])
v2 = np.array([0,1])

A = np.column_stack((v1, v2))

print(A)
```

------------------------------------------------------------------------

# 13. NumPy Rank

``` python
import numpy as np

A = np.array([[1,0],
              [0,1]])

print(np.linalg.matrix_rank(A))
```

The matrix rank tells us how many independent vectors it contains.

------------------------------------------------------------------------

# 14. Common Mistakes

❌ Confusing basis with dimension.

❌ Assuming more dimensions always mean better models.

❌ Ignoring redundant features.

------------------------------------------------------------------------

# 15. Interview Questions

### Basic

What is a basis?

The minimum set of independent vectors that can generate an entire
vector space.

### Intermediate

What is the dimension of a vector space?

The number of vectors in its basis.

### Advanced

Why is dimensionality reduction useful in Machine Learning?

It reduces computation, memory usage, and noise while preserving useful
information.

------------------------------------------------------------------------

# 16. Quick Revision

``` text
Vector Space
      │
      ▼
Independent Vectors
      │
      ▼
Basis
      │
      ▼
Dimension
      │
      ▼
PCA
      │
      ▼
Embeddings
```

------------------------------------------------------------------------

# Lesson Summary

-   A basis is the smallest independent set of vectors needed to
    describe a space.
-   Dimension is the number of vectors in that basis.
-   High-dimensional spaces are common in AI.
-   Dimensionality reduction helps make AI models faster and more
    efficient.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 21

Linear Transformations

↓

How AI Changes Data from One Space to Another
```
