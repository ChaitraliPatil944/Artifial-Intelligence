# Lesson 15: Vectors

## Part III -- Mathematics for AI

> **Goal:** Understand what vectors are, why they were invented, and why
> they are one of the most important concepts in Artificial
> Intelligence.

------------------------------------------------------------------------

# Estimated Reading Time

45--60 Minutes

# Difficulty

⭐⭐⭐☆☆

# Prerequisites

-   Lesson 13 -- Basic Mathematics Refresher
-   Lesson 14 -- Linear Algebra

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson, you will be able to:

-   Explain what a vector is.
-   Differentiate between scalars and vectors.
-   Represent vectors mathematically.
-   Calculate vector magnitude.
-   Understand vector direction.
-   Perform basic vector operations.
-   Explain how vectors are used in AI.

------------------------------------------------------------------------

# 1. Why Were Vectors Invented?

Imagine giving directions to a friend.

If you only say:

``` text
Walk 5 km
```

Something is missing.

Which direction?

North?

South?

East?

West?

A single number cannot describe movement completely.

Mathematicians introduced **vectors** to represent both **magnitude**
and **direction**.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine you tell a child:

``` text
Take 5 steps.
```

The child asks,

> "Which way?"

Now you say:

``` text
Take 5 steps
towards the playground.
```

Now the instruction is complete.

A vector works exactly like this.

It answers:

-   How much?
-   Which direction?

------------------------------------------------------------------------

# 3. Scalars vs Vectors

A scalar has only magnitude.

Examples:

-   Temperature
-   Age
-   Weight
-   Salary

A vector has magnitude **and** direction.

Examples:

-   Velocity
-   Force
-   Displacement
-   Wind

``` text
Scalar

50 km/h

Vector

50 km/h East
```

------------------------------------------------------------------------

# 4. Definition

A **vector** is a mathematical object that has:

-   Magnitude (size)
-   Direction

In AI, vectors are also used to represent data, even when physical
direction is not involved.

------------------------------------------------------------------------

# 5. Representing a Vector

A 2D vector:

``` text
A = (3, 4)
```

Visual representation:

``` text
y
^
|
|        ● (3,4)
|      /
|    /
|  /
|/
+--------------------> x
```

The arrow from the origin represents the vector.

------------------------------------------------------------------------

# 6. Magnitude

Magnitude tells us the length of the vector.

For:

``` text
A = (3,4)
```

Magnitude:

``` text
|A| = √(3² + 4²)

= √25

= 5
```

------------------------------------------------------------------------

# 7. Direction

Direction tells us where the vector points.

``` text
North

↓

South

← West     East →

↑
```

Two vectors can have the same magnitude but different directions.

------------------------------------------------------------------------

# 8. Types of Vectors

## Zero Vector

``` text
(0,0)
```

Magnitude = 0

------------------------------------------------------------------------

## Unit Vector

Magnitude = 1

Used to represent direction only.

------------------------------------------------------------------------

## Position Vector

Represents the position of a point from the origin.

------------------------------------------------------------------------

## Negative Vector

Points in the opposite direction.

------------------------------------------------------------------------

# 9. Vector Addition

``` text
A = (2,3)

B = (1,4)

A + B = (3,7)
```

------------------------------------------------------------------------

# 10. Vector Subtraction

``` text
A = (5,4)

B = (2,1)

A − B = (3,3)
```

------------------------------------------------------------------------

# 11. Scalar Multiplication

Multiply every component.

``` text
2 × (3,4)

=

(6,8)
```

------------------------------------------------------------------------

# 12. Dot Product

The dot product measures how similar two vectors are.

``` text
A · B

=

A₁B₁ + A₂B₂ + ...
```

Example:

``` text
(2,3)

·

(4,5)

=

2×4 + 3×5

=

23
```

In AI, cosine similarity is built on the dot product.

------------------------------------------------------------------------

# 13. Why AI Loves Vectors

Everything becomes a vector.

``` text
Person

↓

Age
Height
Weight
Salary

↓

Feature Vector

[22,170,60,50000]
```

------------------------------------------------------------------------

# 14. Images as Vectors

``` text
Image

↓

Pixels

↓

Numbers

↓

Vector
```

Every image processed by AI is converted into vectors.

------------------------------------------------------------------------

# 15. Words as Vectors

``` text
Dog

↓

Embedding

↓

[0.13, -0.72, 1.04, ...]
```

Words become vectors so computers can compare meanings.

------------------------------------------------------------------------

# 16. Sentences as Vectors

``` text
"I love AI"

↓

Sentence Embedding

↓

Vector
```

Used in search engines and chatbots.

------------------------------------------------------------------------

# 17. Recommendation Systems

Netflix:

``` text
User

↓

User Vector

Movie

↓

Movie Vector

↓

Similarity

↓

Recommendation
```

------------------------------------------------------------------------

# 18. Neural Networks

``` text
Input Features

↓

Vector

↓

Weight Matrix

↓

Prediction
```

Every layer processes vectors.

------------------------------------------------------------------------

# 19. Python Example

``` python
vector = [2, 4, 6]

print(vector)
```

------------------------------------------------------------------------

# 20. NumPy Example

``` python
import numpy as np

v = np.array([2,4,6])

print(v)
```

------------------------------------------------------------------------

# 21. Common Mistakes

❌ Thinking vectors are only arrows.

❌ Confusing vectors with matrices.

❌ Ignoring vectors because libraries handle them.

------------------------------------------------------------------------

# 22. Interview Questions

### Basic

What is a vector?

A quantity with magnitude and direction. In AI, vectors are also
numerical representations of data.

------------------------------------------------------------------------

### Intermediate

Why are vectors important in AI?

Because almost every type of data is represented as vectors before
processing.

------------------------------------------------------------------------

### Advanced

How are vectors used in LLMs?

Words, sentences, and documents are converted into embedding vectors
that capture semantic meaning.

------------------------------------------------------------------------

# 23. Quick Revision

``` text
Vector

↓

Magnitude

↓

Direction

↓

Operations

↓

Feature Vectors

↓

Embeddings

↓

Neural Networks

↓

Transformers

↓

LLMs
```

------------------------------------------------------------------------

# Lesson Summary

-   Vectors describe magnitude and direction.
-   AI represents almost every type of data as vectors.
-   Feature vectors, embeddings, and neural network inputs are all
    vectors.
-   Vectors are the foundation of modern Machine Learning and Deep
    Learning.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 16

Matrices

↓

Organizing Thousands and Millions of Vectors
```
