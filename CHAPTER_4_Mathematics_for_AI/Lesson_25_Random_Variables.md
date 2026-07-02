# Lesson 25: Random Variables

## Part III -- Mathematics for AI

> **Goal:** Understand what random variables are, why they were
> introduced, and how they are used in Machine Learning, Deep Learning,
> and AI.

------------------------------------------------------------------------

# Estimated Reading Time

75--90 Minutes

# Difficulty

⭐⭐⭐☆☆

# Prerequisites

-   Lessons 13--24

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson you will be able to:

-   Explain what a random variable is.
-   Differentiate discrete and continuous random variables.
-   Understand probability distributions.
-   Calculate expected value.
-   Understand variance intuitively.
-   Explain why AI models use random variables.

------------------------------------------------------------------------

# 1. Why Were Random Variables Invented?

Suppose you roll a dice.

You don't know the outcome beforehand.

Instead of writing:

``` text
1
2
3
4
5
6
```

mathematicians created a symbol to represent the unknown result.

That symbol is called a **random variable**.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine a mystery gift box.

``` text
🎁

?
```

You know it contains **one toy**, but not which one.

The unknown toy is like a random variable.

When the box is opened, the random variable gets a value.

------------------------------------------------------------------------

# 3. Definition

A **random variable** is a variable whose value depends on the outcome
of a random event.

Example:

``` text
X = Result of Rolling a Dice
```

Possible values:

``` text
1,2,3,4,5,6
```

------------------------------------------------------------------------

# 4. Why Is It Called "Random"?

The **variable** is not random.

The **value it receives** is random.

``` text
X

↓

Unknown

↓

Roll Dice

↓

X = 4
```

------------------------------------------------------------------------

# 5. Types of Random Variables

## Discrete Random Variable

Can take **countable** values.

Examples:

-   Dice roll
-   Number of emails
-   Number of customers

``` text
0
1
2
3
...
```

------------------------------------------------------------------------

## Continuous Random Variable

Can take **any value in a range**.

Examples:

-   Height
-   Weight
-   Temperature
-   Time

``` text
168.2 cm

168.25 cm

168.253 cm
```

------------------------------------------------------------------------

# 6. Probability Distribution

A probability distribution tells us how likely each value is.

Dice:

``` text
Value   Probability

1       1/6
2       1/6
3       1/6
4       1/6
5       1/6
6       1/6
```

------------------------------------------------------------------------

# 7. Expected Value

Expected value is the **long-term average**.

Think of rolling a dice thousands of times.

Formula:

``` text
Expected Value

=

Σ (Value × Probability)
```

For a fair dice:

``` text
E(X)=3.5
```

You never roll a 3.5.

It represents the average over many rolls.

------------------------------------------------------------------------

# 8. Variance (Intuition)

Variance measures how spread out values are.

Small variance:

``` text
9
10
11
10
```

Large variance:

``` text
1
10
18
4
```

Higher variance means greater uncertainty.

------------------------------------------------------------------------

# 9. Why AI Uses Random Variables

Imagine predicting house prices.

Features:

``` text
Area

Bedrooms

Age
```

These values vary from house to house.

AI treats them as random variables because future inputs are unknown.

------------------------------------------------------------------------

# 10. Machine Learning Example

Spam Detection

``` text
Incoming Email

↓

Random Variable

↓

Model

↓

Spam Probability
```

------------------------------------------------------------------------

# 11. Large Language Models

The next token is unknown.

``` text
"I love"

↓

Next Token

↓

Random Variable

↓

Probability Distribution

↓

Chosen Word
```

------------------------------------------------------------------------

# 12. Medical AI

``` text
Patient Symptoms

↓

Random Variables

↓

Disease Prediction
```

------------------------------------------------------------------------

# 13. Python Example

``` python
import random

X = random.randint(1,6)

print(X)
```

Each execution may produce a different value.

------------------------------------------------------------------------

# 14. Common Mistakes

❌ Thinking the variable itself is random.

❌ Confusing random variables with probability.

❌ Assuming expected value is always an actual outcome.

------------------------------------------------------------------------

# 15. Interview Questions

### Basic

What is a random variable?

A variable whose value depends on the outcome of a random experiment.

### Intermediate

What is the difference between discrete and continuous random variables?

Discrete variables take countable values, while continuous variables can
take any value within an interval.

### Advanced

Why are random variables important in AI?

They model uncertain inputs, outputs, and events, enabling probabilistic
reasoning in machine learning.

------------------------------------------------------------------------

# 16. Quick Revision

``` text
Random Experiment
        │
        ▼
Random Variable
        │
        ├── Discrete
        └── Continuous
               │
               ▼
Probability Distribution
               │
               ▼
Expected Value
               │
               ▼
Variance
```

------------------------------------------------------------------------

# Lesson Summary

-   A random variable represents the outcome of a random experiment.
-   Random variables are either discrete or continuous.
-   Probability distributions describe how likely each value is.
-   Expected value represents the long-term average.
-   Variance measures spread.
-   AI models frequently treat inputs and outputs as random variables.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 26

Probability Distributions

↓

Understanding How Random Variables Behave
```
