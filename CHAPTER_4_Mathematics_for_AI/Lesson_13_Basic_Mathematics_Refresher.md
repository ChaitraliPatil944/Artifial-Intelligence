# Chapter 13: Basic Mathematics Refresher

## Part III -- Mathematics for AI

> **Goal:** Refresh the mathematical foundations required to understand
> Machine Learning, Deep Learning, Computer Vision, NLP, and Large
> Language Models.

------------------------------------------------------------------------

# Learning Objectives

By the end of this chapter you will be able to:

-   Understand the mathematical language used in AI.
-   Recognize the number systems used in computing.
-   Understand variables, constants, expressions, and equations.
-   Understand mathematical functions.
-   Read graphs.
-   Understand coordinates.
-   Understand exponents and logarithms.
-   Read sigma notation.
-   Prepare for Linear Algebra.

------------------------------------------------------------------------

# 1. Why Mathematics Matters in AI

Programming tells the computer **what to do**.

Mathematics tells the computer **how to reason about numbers and
patterns**.

``` text
Data
 │
 ▼
Mathematics
 │
 ▼
Machine Learning
 │
 ▼
Predictions
```

------------------------------------------------------------------------

# 2. Number Systems

AI mainly works with **real numbers**, but understanding the hierarchy
is useful.

``` text
Natural Numbers
      │
      ▼
Whole Numbers
      │
      ▼
Integers
      │
      ▼
Rational Numbers
      │
      ▼
Real Numbers
      │
      ▼
Complex Numbers
```

## Natural Numbers

``` text
1 2 3 4 5 ...
```

Used for counting.

------------------------------------------------------------------------

## Whole Numbers

``` text
0 1 2 3 4 ...
```

Includes zero.

------------------------------------------------------------------------

## Integers

``` text
... -3 -2 -1 0 1 2 3 ...
```

Include negative numbers.

------------------------------------------------------------------------

## Rational Numbers

Numbers that can be written as a fraction.

Examples:

``` text
1/2
3/4
-5/8
```

------------------------------------------------------------------------

## Irrational Numbers

Cannot be written as exact fractions.

Examples:

``` text
π
√2
e
```

------------------------------------------------------------------------

## Real Numbers

Combination of rational and irrational numbers.

Examples:

``` text
-4
0
3.14
√5
```

Most AI calculations use real numbers.

------------------------------------------------------------------------

## Complex Numbers

``` text
a + bi
```

Less common in traditional Machine Learning but useful in some advanced
signal processing and physics applications.

------------------------------------------------------------------------

# 3. Variables

A variable stores a value that may change.

``` text
Age = 22
Salary = 50000
Temperature = 31
```

Python:

``` python
age = 22
```

------------------------------------------------------------------------

# 4. Constants

A constant never changes during a calculation.

Examples:

``` text
π = 3.14159...

e = 2.71828...
```

------------------------------------------------------------------------

# 5. Mathematical Expressions

An expression combines numbers, variables, and operators.

``` text
2x + 5

a + b

x² + y²
```

------------------------------------------------------------------------

# 6. Equations

An equation states that two expressions are equal.

``` text
2x + 5 = 15
```

Machine Learning algorithms learn equations from data.

------------------------------------------------------------------------

# 7. Functions

A function maps an input to an output.

``` text
Input
  │
  ▼
Function
  │
  ▼
Output
```

Example:

``` text
Hours Studied
      │
      ▼
Estimated Marks
```

Notation:

``` text
f(x) = 2x + 1
```

------------------------------------------------------------------------

# 8. Graphs

Graphs help us visualize relationships.

``` text
Marks
 ^
 |
 |          *
 |       *
 |    *
 | *
 +------------------------>
   Hours Studied
```

Many ML algorithms learn these relationships automatically.

------------------------------------------------------------------------

# 9. Coordinate System

``` text
          y
          ^
          |
     II   |   I
----------+----------> x
     III  |   IV
          |
```

Coordinates describe positions.

Example:

``` text
(2,3)
(-1,5)
```

Coordinates naturally lead to vectors in the next chapters.

------------------------------------------------------------------------

# 10. Exponents

Examples:

``` text
2² = 4

2³ = 8

10² = 100
```

Exponents appear frequently in AI formulas.

------------------------------------------------------------------------

# 11. Logarithms

A logarithm answers:

> "What exponent produced this number?"

Example:

``` text
10² = 100

log₁₀(100)=2
```

Logarithms are used in:

-   Cross-Entropy Loss
-   Information Theory
-   Neural Networks

------------------------------------------------------------------------

# 12. Sigma Notation (Σ)

Sigma means **sum**.

Instead of:

``` text
1 + 2 + 3 + 4 + 5
```

We write:

``` text
Σ i
```

Sigma notation appears throughout Machine Learning equations.

------------------------------------------------------------------------

# 13. Factorials

``` text
5! = 5 × 4 × 3 × 2 × 1 = 120
```

Used in probability and combinatorics.

------------------------------------------------------------------------

# 14. Basic Trigonometry

Only a preview.

Important concepts:

-   Sine
-   Cosine
-   Angle

Cosine becomes very important later in:

-   Cosine Similarity
-   Word Embeddings
-   Recommendation Systems
-   Vector Search

------------------------------------------------------------------------

# 15. AI Connections

``` text
Variables
    │
    ▼
Functions
    │
    ▼
Vectors
    │
    ▼
Matrices
    │
    ▼
Neural Networks
    │
    ▼
Transformers
```

Everything builds on these basics.

------------------------------------------------------------------------

# 16. Common Mistakes

-   Memorizing formulas without understanding them.
-   Ignoring graphs.
-   Confusing expressions with equations.
-   Skipping logarithms because they seem difficult.

------------------------------------------------------------------------

# 17. Interview Questions

### Basic

What is a function?

A mapping from an input to an output.

### Intermediate

Why are logarithms important in AI?

They are used in loss functions, probabilities, and information theory.

### Advanced

Why do Machine Learning algorithms rely on mathematical functions?

Because they model relationships between inputs and outputs
mathematically.

------------------------------------------------------------------------

# 18. Quick Revision

``` text
Numbers
   │
Variables
   │
Expressions
   │
Equations
   │
Functions
   │
Graphs
   │
Coordinates
   │
Exponents
   │
Logarithms
   │
Sigma
   │
Vectors (Next Chapter)
```

------------------------------------------------------------------------

# Chapter Summary

-   Mathematics is the foundation of AI.
-   Variables represent changing values.
-   Functions model relationships.
-   Graphs visualize patterns.
-   Logarithms and exponents are common in AI formulas.
-   Sigma notation represents repeated summation.
-   This chapter prepares you for Linear Algebra.

------------------------------------------------------------------------

# Next Chapter

``` text
Chapter 14

Linear Algebra

↓

Vectors

↓

Matrices

↓

Machine Learning
```
