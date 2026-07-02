# Lesson 24: Probability

## Part III -- Mathematics for AI

> **Goal:** Understand probability from first principles and learn why
> AI uses probability to reason under uncertainty.

------------------------------------------------------------------------

# Estimated Reading Time

75--90 Minutes

# Difficulty

⭐⭐⭐☆☆

# Prerequisites

-   Lessons 13--23

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson you will be able to:

-   Explain what probability is.
-   Understand why probability was invented.
-   Calculate simple probabilities.
-   Distinguish independent and dependent events.
-   Connect probability to Machine Learning and Large Language Models.

------------------------------------------------------------------------

# 1. Why Was Probability Invented?

Imagine you ask:

``` text
Will it rain tomorrow?
```

No one can answer with complete certainty.

Instead, we estimate the chance.

Probability was invented to measure **uncertainty**.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine a bag with:

``` text
🎈 Red Ball
🎈 Blue Ball
🎈 Green Ball
🎈 Yellow Ball
```

If you close your eyes and pick one ball,

"What are the chances of picking the red one?"

That chance is probability.

------------------------------------------------------------------------

# 3. Definition

**Probability** is a numerical measure of how likely an event is to
happen.

Its value always lies between:

``` text
0 --------------- 1

Impossible   Certain
```

or

``` text
0% ----------- 100%
```

------------------------------------------------------------------------

# 4. Everyday Examples

``` text
Coin Toss

Heads = 50%

Tails = 50%
```

``` text
Dice

Rolling a 6

1 chance out of 6
```

``` text
Weather

Rain = 80%
```

------------------------------------------------------------------------

# 5. Formula

``` text
Probability

=

Favorable Outcomes
-------------------
Total Outcomes
```

Example:

``` text
Dice

Favorable = 1

Total = 6

P(6) = 1/6
```

------------------------------------------------------------------------

# 6. Sample Space

The **sample space** is the set of all possible outcomes.

Coin:

``` text
S = {Heads, Tails}
```

Dice:

``` text
S = {1,2,3,4,5,6}
```

------------------------------------------------------------------------

# 7. Event

An **event** is any outcome or group of outcomes.

Example:

``` text
Rolling an even number

{2,4,6}
```

------------------------------------------------------------------------

# 8. Independent Events

One event does not affect another.

Example:

``` text
Coin Toss

↓

Roll Dice
```

The coin result does not change the dice result.

------------------------------------------------------------------------

# 9. Dependent Events

One event changes the probability of another.

Example:

Picking cards without replacement.

------------------------------------------------------------------------

# 10. Conditional Probability

Sometimes probability depends on prior knowledge.

Example:

``` text
Student is absent.

↓

Probability of failing increases.
```

This idea leads to Bayes' Theorem.

------------------------------------------------------------------------

# 11. Why AI Uses Probability

AI rarely says:

``` text
Definitely Cat
```

Instead it says:

``` text
Cat

98%
```

Probability allows AI to express confidence.

------------------------------------------------------------------------

# 12. Machine Learning Example

Spam Detection

``` text
Email

↓

Model

↓

Spam = 99%

Not Spam = 1%
```

------------------------------------------------------------------------

# 13. Large Language Models

ChatGPT predicts the next word using probabilities.

``` text
"I love"

↓

AI      62%

Pizza   18%

Music   10%

Coding  10%
```

The next token is chosen from a probability distribution.

------------------------------------------------------------------------

# 14. Self-Driving Cars

``` text
Camera

↓

AI

↓

Pedestrian

96%
```

Probability helps the car make safe decisions.

------------------------------------------------------------------------

# 15. Python Example

``` python
favorable = 1
total = 6

probability = favorable / total

print(probability)
```

Output:

``` text
0.1667
```

------------------------------------------------------------------------

# 16. Common Mistakes

❌ Thinking 80% means certainty.

❌ Confusing possibility with probability.

❌ Assuming AI predictions are always correct.

------------------------------------------------------------------------

# 17. Interview Questions

### Basic

What is probability?

A measure of how likely an event is to occur.

### Intermediate

Why is probability important in AI?

Because AI works with uncertainty and expresses predictions as
confidence scores.

### Advanced

How do Large Language Models use probability?

They calculate a probability distribution over possible next tokens and
generate text by selecting from that distribution.

------------------------------------------------------------------------

# 18. Quick Revision

``` text
Uncertainty
      │
      ▼
Probability
      │
      ▼
Events
      │
      ▼
Sample Space
      │
      ▼
Machine Learning
      │
      ▼
LLMs
```

------------------------------------------------------------------------

# Lesson Summary

-   Probability measures uncertainty.
-   Values range from 0 to 1.
-   Sample spaces contain all possible outcomes.
-   AI uses probabilities instead of absolute certainty.
-   LLMs generate text using probability distributions.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 25

Random Variables

↓

Representing Random Events with Mathematics
```
