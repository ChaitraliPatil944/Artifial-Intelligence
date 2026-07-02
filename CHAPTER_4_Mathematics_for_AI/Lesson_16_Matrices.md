# Lesson 16: Matrices

## Part III -- Mathematics for AI

> **Goal:** Understand what matrices are, why they were invented, and
> why they are one of the most important mathematical structures in
> Artificial Intelligence.

------------------------------------------------------------------------

# Estimated Reading Time

50--60 Minutes

# Difficulty

⭐⭐⭐☆☆

# Prerequisites

-   Lesson 13 -- Basic Mathematics Refresher
-   Lesson 14 -- Linear Algebra
-   Lesson 15 -- Vectors

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson, you will be able to:

-   Explain what a matrix is.
-   Understand rows and columns.
-   Differentiate vectors and matrices.
-   Identify common matrix types.
-   Understand why matrices are used in AI.
-   Read matrix notation.

------------------------------------------------------------------------

# 1. Why Were Matrices Invented?

Imagine Netflix.

It has millions of users and hundreds of thousands of movies.

Storing one user at a time is inefficient.

Instead, organize everything into a table.

``` text
            Movies
         M1 M2 M3 M4
Users U1  5  4  0  3
      U2  3  5  2  0
      U3  0  4  5  5
```

This table is a matrix.

Matrices allow computers to organize and process huge amounts of data
efficiently.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine a classroom.

``` text
      English  Math  Science

Aarav      90    85      88

Riya       95    92      90

Meera      82    80      91
```

Every row represents a student.

Every column represents a subject.

The complete table is a matrix.

------------------------------------------------------------------------

# 3. Definition

A **matrix** is a rectangular arrangement of numbers organized into
**rows** and **columns**.

General notation:

``` text
A =
[a11 a12 a13
 a21 a22 a23
 a31 a32 a33]
```

------------------------------------------------------------------------

# 4. Matrix Dimensions

A matrix with:

-   3 rows
-   4 columns

is written as:

``` text
3 × 4
```

Rule:

``` text
Rows × Columns
```

------------------------------------------------------------------------

# 5. Matrix vs Vector

``` text
Vector

[2 5 8]
```

One-dimensional collection.

``` text
Matrix

[2 5 8
 1 7 9
 4 3 6]
```

Two-dimensional collection.

Think of a matrix as multiple vectors stacked together.

------------------------------------------------------------------------

# 6. Matrix Representation

``` text
Columns →

      1   2   3

R1    2   5   8

R2    4   7   1

R3    9   6   3

Rows ↓
```

Each value has a position.

Example:

``` text
A(2,3)=1
```

Second row, third column.

------------------------------------------------------------------------

# 7. Types of Matrices

## Row Matrix

``` text
[2 4 6]
```

------------------------------------------------------------------------

## Column Matrix

``` text
[2
 4
 6]
```

------------------------------------------------------------------------

## Square Matrix

``` text
[1 2
 3 4]
```

Rows = Columns.

------------------------------------------------------------------------

## Identity Matrix

``` text
[1 0 0
 0 1 0
 0 0 1]
```

Acts like the number 1 in matrix mathematics.

------------------------------------------------------------------------

## Zero Matrix

``` text
[0 0
 0 0]
```

All elements are zero.

------------------------------------------------------------------------

# 8. Why AI Uses Matrices

Images are stored as matrices.

Example:

``` text
150 140 132

120 110 108

 98 102 115
```

Every pixel becomes a matrix value.

------------------------------------------------------------------------

# 9. Images

``` text
Image

↓

Pixel Grid

↓

Matrix

↓

CNN
```

Computer Vision begins with matrices.

------------------------------------------------------------------------

# 10. Neural Networks

``` text
Input Vector

↓

Weight Matrix

↓

Output Vector
```

Every neural network performs matrix operations repeatedly.

------------------------------------------------------------------------

# 11. Recommendation Systems

``` text
Users × Movies

↓

Matrix

↓

Recommendations
```

------------------------------------------------------------------------

# 12. Natural Language Processing

``` text
Words

↓

Embedding Vectors

↓

Embedding Matrix
```

Transformers operate on matrices.

------------------------------------------------------------------------

# 13. Python Example

``` python
matrix = [
    [1,2,3],
    [4,5,6]
]

print(matrix)
```

------------------------------------------------------------------------

# 14. NumPy Example

``` python
import numpy as np

A = np.array([
    [1,2,3],
    [4,5,6]
])

print(A.shape)
```

------------------------------------------------------------------------

# 15. Common Mistakes

❌ Confusing rows and columns.

❌ Thinking a matrix is just an Excel sheet.

❌ Forgetting matrix dimensions.

------------------------------------------------------------------------

# 16. Interview Questions

### Basic

What is a matrix?

A rectangular arrangement of numbers organized into rows and columns.

------------------------------------------------------------------------

### Intermediate

Why are matrices important in AI?

They efficiently represent and process large amounts of numerical data
such as images, embeddings, and neural network weights.

------------------------------------------------------------------------

### Advanced

How are matrices used in neural networks?

Inputs, weights, activations, and outputs are represented and
manipulated using matrix operations.

------------------------------------------------------------------------

# 17. Quick Revision

``` text
Numbers

↓

Vectors

↓

Matrices

↓

Matrix Operations

↓

Neural Networks

↓

Deep Learning

↓

Transformers
```

------------------------------------------------------------------------

# Lesson Summary

-   A matrix is a rectangular arrangement of numbers.
-   Matrices are built from rows and columns.
-   Images, embeddings, and neural networks all use matrices.
-   Matrix dimensions are fundamental to AI computations.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 17

Matrix Operations

↓

How AI Performs Calculations Efficiently
```
