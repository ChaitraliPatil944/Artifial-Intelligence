# Lesson 18: Systems of Linear Equations

## Part III -- Mathematics for AI

> **Goal:** Understand what systems of linear equations are, why they
> were invented, how they are solved, and why they are important in
> Artificial Intelligence.

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

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson, you will be able to:

-   Explain what a system of linear equations is.
-   Solve systems using substitution and elimination.
-   Represent systems as matrices.
-   Understand why solving many unknowns efficiently is important.
-   Connect systems of equations to Machine Learning.

------------------------------------------------------------------------

# 1. Why Were Systems of Equations Invented?

Imagine a shop sells:

-   Pencil = ?
-   Notebook = ?

You only know:

``` text
2 Pencils + 1 Notebook = ₹50

1 Pencil + 2 Notebooks = ₹70
```

One equation is not enough.

You need multiple equations to solve multiple unknowns.

------------------------------------------------------------------------

# 2. Definition

A **system of linear equations** is a collection of two or more linear
equations involving the same variables.

Example:

``` text
2x + y = 5

x - y = 1
```

The goal is to find values of **x** and **y** that satisfy every
equation.

------------------------------------------------------------------------

# 3. Child Analogy

Imagine two treasure maps.

Only the place where both maps point is the real treasure.

Likewise, the solution is where **all equations agree**.

------------------------------------------------------------------------

# 4. Graphical Intuition

``` text
y
^
|    /
|   /
|  X  ← Solution
| /
|/
+--------------> x
```

The intersection point is the solution.

------------------------------------------------------------------------

# 5. Solving by Substitution

Example:

``` text
x + y = 8

x = 3
```

Replace:

``` text
3 + y = 8

y = 5
```

Solution:

``` text
x = 3

y = 5
```

------------------------------------------------------------------------

# 6. Solving by Elimination

Example:

``` text
2x + y = 7

2x - y = 5
```

Add both equations:

``` text
4x = 12

x = 3
```

Substitute back:

``` text
y = 1
```

------------------------------------------------------------------------

# 7. Matrix Representation

A system:

``` text
2x + y = 5

x + 3y = 10
```

Can be written as:

``` text
Coefficient Matrix

[2 1
 1 3]

×

Variable Vector

[x
 y]

=

Result Vector

[5
10]
```

This compact representation is used throughout AI.

------------------------------------------------------------------------

# 8. Why AI Uses Matrix Form

Instead of solving equations one at a time:

``` text
Equation 1

Equation 2

Equation 3

...

Equation 1,000,000
```

AI solves many relationships simultaneously using matrix operations.

------------------------------------------------------------------------

# 9. Real AI Example

Suppose each feature contributes to predicting house price.

``` text
Area

Bedrooms

Age

↓

Model

↓

House Price
```

The relationship can be represented using systems of equations.

------------------------------------------------------------------------

# 10. Computer Vision Example

``` text
Pixel Values

↓

Matrix

↓

Linear Equations

↓

Image Transformation
```

------------------------------------------------------------------------

# 11. Neural Network Connection

Each neuron computes:

``` text
Weights × Inputs

↓

Linear Equation

↓

Activation
```

Millions of these equations work together inside deep learning models.

------------------------------------------------------------------------

# 12. Python Example

``` python
import numpy as np

A = np.array([[2,1],
              [1,3]])

b = np.array([5,10])

x = np.linalg.solve(A,b)

print(x)
```

------------------------------------------------------------------------

# 13. Common Mistakes

❌ Assuming every system has one solution.

Possible cases:

-   One solution
-   No solution
-   Infinite solutions

❌ Forgetting that equations must be independent.

------------------------------------------------------------------------

# 14. Interview Questions

### Basic

What is a system of linear equations?

A set of linear equations solved together to determine unknown
variables.

### Intermediate

Why are matrices used to represent systems?

Because they provide an efficient way to solve many equations
simultaneously.

### Advanced

How are systems of equations related to Machine Learning?

Many ML models can be expressed as matrix equations, allowing efficient
computation on large datasets.

------------------------------------------------------------------------

# 15. Quick Revision

``` text
Multiple Equations
        │
        ▼
Unknown Variables
        │
        ▼
Matrix Form
        │
        ▼
Efficient Solution
        │
        ▼
Machine Learning
```

------------------------------------------------------------------------

# Lesson Summary

-   Systems of linear equations solve multiple unknowns at once.
-   Matrices provide a compact representation.
-   Matrix methods scale to millions of equations.
-   AI models rely heavily on solving linear relationships efficiently.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 19

Vector Spaces

↓

Understanding the Space Where Vectors Live
```
