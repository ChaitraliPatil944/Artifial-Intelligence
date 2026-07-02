# Lesson 26: Probability Distributions

## Part III -- Mathematics for AI

> **Goal:** Understand probability distributions, why they were
> invented, and how they help AI model uncertainty.

------------------------------------------------------------------------

# Estimated Reading Time

80--90 Minutes

# Difficulty

⭐⭐⭐⭐☆

# Prerequisites

-   Lessons 13--25

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson you will be able to:

-   Explain what a probability distribution is.
-   Distinguish PMF, PDF, and CDF.
-   Understand common distributions used in AI.
-   Explain why the Normal Distribution appears so often.
-   Connect probability distributions to Machine Learning.

------------------------------------------------------------------------

# 1. Why Were Probability Distributions Invented?

Knowing possible outcomes is useful.

Knowing **how likely** each outcome is is even more useful.

Example:

``` text
Exam Marks

20

40

60

80

100
```

How often does each mark occur?

A probability distribution answers that question.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine a candy jar.

``` text
🍬 Red    50

🍬 Blue   30

🍬 Green  20
```

A distribution describes how the candies are spread.

Probability distributions describe how values are spread.

------------------------------------------------------------------------

# 3. Definition

A **probability distribution** describes how probabilities are assigned
to the values of a random variable.

``` text
Random Variable
        │
        ▼
Possible Values
        │
        ▼
Probability of Each Value
```

------------------------------------------------------------------------

# 4. PMF (Probability Mass Function)

Used for **discrete** random variables.

Example:

``` text
Dice

Value   Probability

1       1/6
2       1/6
3       1/6
4       1/6
5       1/6
6       1/6
```

------------------------------------------------------------------------

# 5. PDF (Probability Density Function)

Used for **continuous** random variables.

Example:

``` text
Height

160.1

160.2

160.3

...
```

A PDF describes density instead of individual probabilities.

------------------------------------------------------------------------

# 6. CDF (Cumulative Distribution Function)

Shows the probability that:

``` text
X ≤ x
```

Example:

``` text
Probability

Score ≤ 80
```

------------------------------------------------------------------------

# 7. Uniform Distribution

Every outcome has the same probability.

``` text
Dice

1 2 3 4 5 6

All = 1/6
```

------------------------------------------------------------------------

# 8. Bernoulli Distribution

Only two outcomes.

``` text
Success

Failure
```

Examples:

-   Email is spam / not spam
-   Pass / Fail
-   Fraud / Not Fraud

------------------------------------------------------------------------

# 9. Binomial Distribution

Repeating Bernoulli experiments.

Example:

``` text
Flip Coin

10 Times

↓

How many Heads?
```

------------------------------------------------------------------------

# 10. Normal (Gaussian) Distribution

The most famous distribution.

``` text
          *
        *   *
      *       *
    *           *
------------------------>
```

Also called the **Bell Curve**.

Many natural measurements approximately follow this pattern.

Examples:

-   Height
-   Weight
-   Exam scores
-   Sensor noise

------------------------------------------------------------------------

# 11. Why AI Loves the Bell Curve

Many optimization methods assume data behaves approximately like a
normal distribution.

It also appears because of the Central Limit Theorem (covered later).

------------------------------------------------------------------------

# 12. AI Applications

## Naive Bayes

``` text
Features

↓

Probability Distribution

↓

Prediction
```

------------------------------------------------------------------------

## Anomaly Detection

``` text
Normal Distribution

↓

Far Away Values

↓

Anomaly
```

------------------------------------------------------------------------

## Deep Learning

Weights are often initialized using probability distributions.

------------------------------------------------------------------------

## LLMs

The next token is selected from a probability distribution over the
vocabulary.

------------------------------------------------------------------------

# 13. Python Example

``` python
import numpy as np

samples = np.random.normal(
    loc=0,
    scale=1,
    size=5
)

print(samples)
```

------------------------------------------------------------------------

# 14. Common Mistakes

❌ Confusing PMF with PDF.

❌ Assuming all data follows a normal distribution.

❌ Thinking a PDF directly gives probability at one exact continuous
value.

------------------------------------------------------------------------

# 15. Interview Questions

### Basic

What is a probability distribution?

A mathematical description of how probabilities are assigned to the
values of a random variable.

### Intermediate

What is the difference between PMF and PDF?

PMF is used for discrete variables, while PDF is used for continuous
variables.

### Advanced

Why is the normal distribution important in Machine Learning?

Many algorithms and statistical methods assume data or errors
approximately follow a normal distribution.

------------------------------------------------------------------------

# 16. Quick Revision

``` text
Random Variable
        │
        ▼
Probability Distribution
        │
 ┌──────┼─────────┐
 │      │         │
PMF    PDF       CDF
 │      │
 ▼      ▼
Discrete Continuous
        │
        ▼
Normal Distribution
        │
        ▼
Machine Learning
```

------------------------------------------------------------------------

# Lesson Summary

-   Probability distributions describe how probabilities are spread.
-   PMF is for discrete variables.
-   PDF is for continuous variables.
-   CDF accumulates probabilities.
-   The Normal Distribution is widely used in AI.
-   Modern AI models frequently rely on probability distributions to
    model uncertainty.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 27

Bayes' Theorem

↓

Updating Beliefs Using New Evidence
```
