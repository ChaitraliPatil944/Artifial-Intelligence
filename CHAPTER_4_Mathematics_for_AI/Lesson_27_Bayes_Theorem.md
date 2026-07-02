# Lesson 27: Bayes' Theorem

## Part III -- Mathematics for AI

> **Goal:** Understand Bayes' Theorem intuitively, learn why it was
> invented, and see how AI updates its beliefs when new evidence
> appears.

------------------------------------------------------------------------

# Estimated Reading Time

80--90 Minutes

# Difficulty

⭐⭐⭐⭐☆

# Prerequisites

-   Lessons 13--26

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson you will be able to:

-   Explain Bayes' Theorem in simple words.
-   Understand prior, likelihood, evidence, and posterior.
-   Apply Bayes' Theorem to simple problems.
-   Explain why Bayesian reasoning is useful in AI.
-   Connect Bayes' Theorem to spam filtering and medical diagnosis.

------------------------------------------------------------------------

# 1. Why Was Bayes' Theorem Invented?

Imagine a doctor says:

``` text
The test is positive.
```

Does that automatically mean the patient has the disease?

Not necessarily.

We need to combine:

-   Previous knowledge
-   New evidence

Bayes' Theorem was invented to update beliefs when new information
becomes available.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine you're a detective.

You first believe:

``` text
Suspect A

50%

Suspect B

50%
```

Then you discover fingerprints.

``` text
New Evidence

↓

Update Belief

↓

Suspect A

90%
```

Bayes' Theorem performs this update mathematically.

------------------------------------------------------------------------

# 3. Definition

Bayes' Theorem calculates the probability of an event after considering
new evidence.

------------------------------------------------------------------------

# 4. The Formula

``` text
           P(B|A) × P(A)
P(A|B) = ----------------
              P(B)
```

Where:

-   P(A\|B) = Posterior
-   P(B\|A) = Likelihood
-   P(A) = Prior
-   P(B) = Evidence

------------------------------------------------------------------------

# 5. Understanding Each Part

## Prior

Your belief **before** seeing new evidence.

Example:

``` text
Chance of Rain

30%
```

------------------------------------------------------------------------

## Likelihood

How likely the evidence is if your assumption is true.

------------------------------------------------------------------------

## Evidence

The probability of observing the evidence.

------------------------------------------------------------------------

## Posterior

Your updated belief after considering the evidence.

------------------------------------------------------------------------

# 6. Visual Pipeline

``` text
Prior Belief
      │
      ▼
New Evidence
      │
      ▼
Bayes' Theorem
      │
      ▼
Updated Belief
```

------------------------------------------------------------------------

# 7. Medical Diagnosis Example

Suppose:

``` text
Disease Rate = 1%

Test Accuracy = 95%

Test Result = Positive
```

Bayes' Theorem helps estimate the true probability that the patient
actually has the disease.

------------------------------------------------------------------------

# 8. Spam Detection

``` text
Incoming Email
        │
        ▼
Contains "Free"
        │
        ▼
Update Spam Probability
        │
        ▼
Spam / Not Spam
```

This is the basic idea behind the Naive Bayes classifier.

------------------------------------------------------------------------

# 9. Self-Driving Cars

``` text
Camera Detects Object
          │
          ▼
Previous Knowledge
          │
          ▼
Update Confidence
          │
          ▼
Pedestrian Probability
```

------------------------------------------------------------------------

# 10. AI Uses of Bayes' Theorem

-   Naive Bayes Classification
-   Medical diagnosis
-   Speech recognition
-   Robotics
-   Sensor fusion
-   Fraud detection
-   Recommendation systems

------------------------------------------------------------------------

# 11. Worked Example

Bag contains:

``` text
3 Red Balls

2 Blue Balls
```

Probability of picking a red ball:

``` text
P(Red) = 3 / 5
```

If extra evidence changes what we know about the bag, Bayes' Theorem
updates this probability accordingly.

------------------------------------------------------------------------

# 12. Python Example

``` python
prior = 0.01
likelihood = 0.95
evidence = 0.05

posterior = (likelihood * prior) / evidence

print(posterior)
```

------------------------------------------------------------------------

# 13. Common Mistakes

❌ Confusing prior with posterior.

❌ Ignoring the evidence term.

❌ Assuming a positive test always means the event is true.

------------------------------------------------------------------------

# 14. Interview Questions

### Basic

What is Bayes' Theorem?

A theorem that updates the probability of an event after observing new
evidence.

### Intermediate

Why is Bayes' Theorem useful in AI?

Because AI systems continuously update predictions as new information
arrives.

### Advanced

How does Naive Bayes use Bayes' Theorem?

It assumes features are conditionally independent and applies Bayes'
Theorem to calculate class probabilities efficiently.

------------------------------------------------------------------------

# 15. Quick Revision

``` text
Prior
  │
  ▼
Evidence
  │
  ▼
Likelihood
  │
  ▼
Bayes' Theorem
  │
  ▼
Posterior
```

------------------------------------------------------------------------

# Lesson Summary

-   Bayes' Theorem updates beliefs using evidence.
-   Prior is the initial belief.
-   Posterior is the updated belief.
-   AI uses Bayesian reasoning to make better predictions under
    uncertainty.
-   Naive Bayes is a practical machine learning algorithm based on
    Bayes' Theorem.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 28

Statistics

↓

Understanding Data Before Building AI Models
```
