# Lesson 21: Linear Transformations

## Part III -- Mathematics for AI

> **Goal:** Understand how linear transformations change vectors from
> one space to another and why they are fundamental to Machine Learning,
> Deep Learning, and Large Language Models.

------------------------------------------------------------------------

# Estimated Reading Time

60--75 Minutes

# Difficulty

⭐⭐⭐⭐☆

# Prerequisites

-   Lessons 13--20

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson, you will be able to:

-   Explain what a linear transformation is.
-   Understand scaling, rotation, reflection and shearing.
-   Represent transformations using matrices.
-   Explain why every neural network layer performs linear
    transformations.
-   Connect transformations to embeddings and AI models.

------------------------------------------------------------------------

# 1. Why Were Linear Transformations Invented?

Imagine you have a map.

You want to:

-   Zoom in
-   Rotate it
-   Flip it
-   Stretch it

The information stays the same, but its representation changes.

Linear transformations were invented to describe these changes
mathematically.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine drawing a square on a rubber sheet.

``` text
□□□□
```

Now stretch the sheet.

``` text
▭▭▭▭
```

The shape changes, but every point moves according to a rule.

That rule is a transformation.

------------------------------------------------------------------------

# 3. Definition

A **linear transformation** is a mathematical function that transforms
one vector into another while preserving linear relationships.

It satisfies:

``` text
T(a + b) = T(a) + T(b)

T(ca) = cT(a)
```

------------------------------------------------------------------------

# 4. Transformation Pipeline

``` text
Input Vector
      │
      ▼
Transformation Matrix
      │
      ▼
Output Vector
```

------------------------------------------------------------------------

# 5. Scaling

Increase or decrease size.

``` text
(2,3)

↓

×2

↓

(4,6)
```

------------------------------------------------------------------------

# 6. Rotation

Rotate a vector around the origin.

``` text
Before

   ↑

After

←
```

Computer graphics and robotics use rotations constantly.

------------------------------------------------------------------------

# 7. Reflection

Mirror a vector.

``` text
Before     After

   /        \
```

------------------------------------------------------------------------

# 8. Shearing

Push one side while keeping the other fixed.

``` text
Square

□□□□

↓

Parallelogram
```

------------------------------------------------------------------------

# 9. Matrix Representation

Every linear transformation can be represented by a matrix.

``` text
Transformation Matrix
        ×
Input Vector
        │
        ▼
Output Vector
```

This is why matrices are central to AI.

------------------------------------------------------------------------

# 10. Why AI Uses Linear Transformations

Every neural network layer computes:

``` text
Input Vector
      │
      ▼
Weight Matrix
      │
      ▼
Linear Transformation
      │
      ▼
Activation Function
      │
      ▼
Next Layer
```

Without linear transformations, neural networks cannot learn useful
representations.

------------------------------------------------------------------------

# 11. Embeddings

``` text
Word

↓

Embedding Vector

↓

Transformation Matrix

↓

New Embedding
```

Transformers repeatedly transform embeddings into richer
representations.

------------------------------------------------------------------------

# 12. Computer Vision

``` text
Image Matrix

↓

Transformation

↓

Feature Extraction
```

CNNs apply learned transformations to detect patterns.

------------------------------------------------------------------------

# 13. Recommendation Systems

``` text
User Vector

↓

Transformation

↓

Latent Space

↓

Recommendation
```

------------------------------------------------------------------------

# 14. Python Example

``` python
import numpy as np

A = np.array([[2,0],
              [0,2]])

v = np.array([2,3])

print(A @ v)
```

Output:

``` text
[4 6]
```

------------------------------------------------------------------------

# 15. Common Mistakes

❌ Thinking transformations only change position.

❌ Forgetting that matrices represent transformations.

❌ Confusing transformations with arbitrary changes.

------------------------------------------------------------------------

# 16. Interview Questions

### Basic

What is a linear transformation?

A rule that maps vectors to vectors while preserving linearity.

### Intermediate

Why are matrices used to represent linear transformations?

Because matrix multiplication efficiently applies the same
transformation to vectors.

### Advanced

Why does every neural network layer perform a linear transformation?

The weight matrix transforms the input into a new feature space before a
non-linear activation function is applied.

------------------------------------------------------------------------

# 17. Quick Revision

``` text
Vectors
    │
    ▼
Matrix
    │
    ▼
Linear Transformation
    │
    ▼
Activation
    │
    ▼
Neural Network
    │
    ▼
Transformer
```

------------------------------------------------------------------------

# Lesson Summary

-   Linear transformations change vectors while preserving linear
    structure.
-   Matrices represent linear transformations.
-   Scaling, rotation, reflection and shearing are common examples.
-   Every neural network layer begins with a linear transformation.
-   Modern AI repeatedly transforms vectors into increasingly meaningful
    representations.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 22

Eigenvalues & Eigenvectors

↓

Finding the Most Important Directions in Data
```
