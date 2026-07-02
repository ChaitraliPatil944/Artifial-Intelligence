# Lesson 33: Hypothesis Testing

## Part III -- Mathematics for AI

> **Goal:** Understand hypothesis testing, why it was invented, and how
> AI engineers use it to make reliable, data-driven decisions.

------------------------------------------------------------------------

# Estimated Reading Time

90 Minutes

# Difficulty

⭐⭐⭐⭐☆

# Prerequisites

-   Lessons 13--32

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson you will be able to:

-   Explain hypothesis testing.
-   Understand the null and alternative hypotheses.
-   Interpret p-values.
-   Understand significance levels.
-   Differentiate Type I and Type II errors.
-   Explain how hypothesis testing is used in AI and A/B testing.

------------------------------------------------------------------------

# 1. Why Was Hypothesis Testing Invented?

Imagine a company launches a new recommendation algorithm.

After one week, sales increase.

Did the new algorithm really improve sales?

Or was it just luck?

Humans needed a mathematical way to answer that question.

Hypothesis testing was invented to distinguish **real effects** from
**random chance**.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine your friend claims:

``` text
"This dice is lucky!"
```

You roll it 100 times.

If it behaves like a normal dice, the claim is probably false.

If it lands on 6 far more often than expected, you start believing the
claim.

Instead of trusting opinions, you test them with evidence.

------------------------------------------------------------------------

# 3. What is Hypothesis Testing?

Hypothesis testing is a statistical method used to decide whether
evidence supports a claim.

``` text
Claim
  │
  ▼
Collect Data
  │
  ▼
Analyze Evidence
  │
  ▼
Decision
```

------------------------------------------------------------------------

# 4. Null Hypothesis (H₀)

The null hypothesis assumes:

> Nothing unusual is happening.

Example:

``` text
New AI model

=

Old AI model
```

No improvement.

------------------------------------------------------------------------

# 5. Alternative Hypothesis (H₁)

The alternative hypothesis assumes:

``` text
New AI Model

>

Old AI Model
```

A meaningful difference exists.

------------------------------------------------------------------------

# 6. Significance Level (α)

Before testing, choose a threshold.

Usually:

``` text
α = 0.05
```

This means you're willing to accept a 5% chance of incorrectly rejecting
H₀.

------------------------------------------------------------------------

# 7. What is a p-value?

The p-value answers:

> "If the null hypothesis were true, how surprising are these results?"

Small p-value:

``` text
Evidence against H₀
```

Large p-value:

``` text
Not enough evidence
```

Rule:

``` text
p < 0.05

↓

Reject H₀
```

------------------------------------------------------------------------

# 8. Decision Flow

``` text
Collect Data
      │
      ▼
Calculate p-value
      │
      ▼
p < α ?
   │
 ┌─┴───────┐
 │         │
Yes        No
 │         │
Reject   Fail to Reject
 H₀          H₀
```

Note: "Fail to reject H₀" is **not** the same as proving H₀ is true.

------------------------------------------------------------------------

# 9. Type I Error

Rejecting a true null hypothesis.

``` text
Reality:
No Improvement

Decision:
Improvement
```

False alarm.

------------------------------------------------------------------------

# 10. Type II Error

Failing to reject a false null hypothesis.

``` text
Reality:
Improvement

Decision:
No Improvement
```

Missed opportunity.

------------------------------------------------------------------------

# 11. A/B Testing

``` text
Version A

↓

Old Website

Version B

↓

New Website

↓

Compare Results
```

Hypothesis testing helps determine whether B genuinely performs better.

------------------------------------------------------------------------

# 12. AI Applications

-   A/B testing
-   Model comparison
-   Drug discovery
-   Fraud detection
-   Marketing analytics
-   Recommendation systems

------------------------------------------------------------------------

# 13. Machine Learning Example

Two classifiers:

``` text
Model A

Accuracy = 92%

Model B

Accuracy = 93%
```

Is the 1% improvement meaningful?

Hypothesis testing helps answer that.

------------------------------------------------------------------------

# 14. Python Example

``` python
from scipy import stats

group_a = [70,72,69,71,73]
group_b = [78,80,79,77,81]

t_stat, p_value = stats.ttest_ind(group_a, group_b)

print(p_value)
```

------------------------------------------------------------------------

# 15. Common Mistakes

❌ p-value is the probability that H₀ is true.

❌ p \< 0.05 proves a theory.

❌ Failing to reject H₀ means H₀ has been proven.

------------------------------------------------------------------------

# 16. Interview Questions

### Basic

What is the null hypothesis?

The default assumption that there is no effect or difference.

### Intermediate

What does a p-value represent?

It measures how compatible the observed data is with the null
hypothesis.

### Advanced

Why is hypothesis testing important in machine learning?

It helps determine whether observed improvements are statistically
meaningful rather than due to random variation.

------------------------------------------------------------------------

# 17. Quick Revision

``` text
Claim
 │
 ▼
H₀ / H₁
 │
 ▼
Collect Data
 │
 ▼
p-value
 │
 ▼
Decision
 │
 ▼
AI Improvement?
```

------------------------------------------------------------------------

# Lesson Summary

-   Hypothesis testing evaluates claims using data.
-   H₀ assumes no effect; H₁ assumes an effect exists.
-   The p-value measures how surprising the data is under H₀.
-   Type I and Type II errors describe two kinds of incorrect decisions.
-   AI engineers use hypothesis testing to validate models and
    experiments.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 34

Calculus

↓

Understanding How AI Learns and Optimizes
```
