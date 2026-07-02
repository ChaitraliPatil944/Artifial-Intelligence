# Lesson 19: Vector Spaces

## Part III -- Mathematics for AI

> **Goal:** Understand what a vector space is, why it was invented, and
> why it is the mathematical foundation for Machine Learning, Deep
> Learning, and Large Language Models.

------------------------------------------------------------------------

# Estimated Reading Time

60 Minutes

# Difficulty

⭐⭐⭐⭐☆

# Prerequisites

-   Lesson 13 -- Basic Mathematics Refresher
-   Lesson 14 -- Linear Algebra
-   Lesson 15 -- Vectors
-   Lesson 16 -- Matrices
-   Lesson 17 -- Matrix Operations
-   Lesson 18 -- Systems of Linear Equations

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson you will be able to:

-   Explain what a vector space is.
-   Understand why vector spaces were introduced.
-   Visualize vectors living inside a space.
-   Understand dimensions of a vector space.
-   Connect vector spaces to embeddings, neural networks, and AI.

------------------------------------------------------------------------

# 1. Why Were Vector Spaces Invented?

Imagine you have a single vector.

``` text
(3,4)
```

Easy.

Now imagine:

-   One thousand vectors.
-   One million vectors.
-   One billion vectors.

Where do all these vectors "live"?

Mathematicians created the idea of a **vector space** to describe the
world in which vectors exist and interact.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine a playground.

``` text
Playground
 ├── Child A
 ├── Child B
 ├── Child C
```

The playground is the **space**.

The children are the **vectors**.

Vectors need a space just as children need somewhere to play.

------------------------------------------------------------------------

# 3. Definition

A **vector space** is a collection of vectors that follows mathematical
rules for addition and scalar multiplication.

If two vectors belong to the same vector space:

-   They can be added.
-   They can be multiplied by scalars.
-   The result still belongs to the same space.

------------------------------------------------------------------------

# 4. A 2D Vector Space

``` text
          y
          ^
     ●
          |
  ●       |
----------+----------> x
      ●
```

Every point represents a vector.

Together they form a 2-dimensional vector space.

------------------------------------------------------------------------

# 5. A 3D Vector Space

``` text
        z
        ^
       /
      /
     O------> y
    /
   /
  x
```

Examples:

``` text
(2,3,5)

(7,1,9)

(4,8,6)
```

These vectors live in 3-dimensional space.

------------------------------------------------------------------------

# 6. Higher Dimensions

Humans easily visualize:

-   2D
-   3D

AI often works in:

-   128 dimensions
-   512 dimensions
-   768 dimensions
-   1536 dimensions
-   4096 dimensions

Even though we cannot draw them, the mathematics remains the same.

------------------------------------------------------------------------

# 7. Why AI Uses High-Dimensional Spaces

Suppose a person has:

-   Age
-   Height
-   Weight
-   Salary

Feature vector:

``` text
[22,170,60,50000]
```

This is one point in a 4-dimensional vector space.

Adding more features increases the number of dimensions.

------------------------------------------------------------------------

# 8. Word Embeddings

The word:

``` text
Dog
```

becomes

``` text
[0.25, -0.71, 1.42, ...]
```

A vector with hundreds or thousands of dimensions.

Words with similar meanings are located close together inside the vector
space.

------------------------------------------------------------------------

# 9. Sentence Embeddings

``` text
"I love AI"

↓

Embedding Model

↓

768-Dimensional Vector
```

Search engines compare these vectors to find similar sentences.

------------------------------------------------------------------------

# 10. Recommendation Systems

``` text
User

↓

User Vector

Movie

↓

Movie Vector

↓

Same Vector Space

↓

Similarity

↓

Recommendation
```

Users and movies must exist in the same vector space for comparison.

------------------------------------------------------------------------

# 11. Neural Networks

``` text
Input Space

↓

Hidden Space

↓

Output Space
```

Neural networks transform vectors from one space into another.

------------------------------------------------------------------------

# 12. Important Properties

A vector space is:

-   Closed under addition
-   Closed under scalar multiplication
-   Contains a zero vector

These rules ensure consistent mathematical behavior.

------------------------------------------------------------------------

# 13. Python Example

``` python
import numpy as np

v1 = np.array([2, 4])
v2 = np.array([1, 3])

print(v1 + v2)
print(3 * v1)
```

------------------------------------------------------------------------

# 14. Common Mistakes

❌ Thinking vector spaces only exist in 2D.

❌ Assuming high-dimensional spaces work differently.

❌ Confusing vectors with the space they belong to.

------------------------------------------------------------------------

# 15. Interview Questions

### Basic

What is a vector space?

A mathematical collection of vectors where vector addition and scalar
multiplication are defined.

### Intermediate

Why are vector spaces important in AI?

They provide the mathematical framework for representing and comparing
data such as images, text, and embeddings.

### Advanced

Why do Large Language Models use high-dimensional vector spaces?

High-dimensional spaces allow models to capture complex semantic
relationships between words, sentences, and documents.

------------------------------------------------------------------------

# 16. Quick Revision

``` text
Vector
   │
   ▼
Vector Space
   │
   ▼
Dimensions
   │
   ▼
Embeddings
   │
   ▼
Neural Networks
   │
   ▼
Transformers
```

------------------------------------------------------------------------

# Lesson Summary

-   A vector space is the environment where vectors exist and interact.
-   AI represents data as vectors inside high-dimensional vector spaces.
-   Word embeddings, image embeddings, and recommendation systems all
    rely on vector spaces.
-   Understanding vector spaces is essential for modern AI.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 20

Basis & Dimension

↓

How AI Represents Complex Information Efficiently
```
