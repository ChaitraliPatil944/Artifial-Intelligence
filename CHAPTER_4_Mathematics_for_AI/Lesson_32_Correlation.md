# Lesson 32: Correlation

## Part III -- Mathematics for AI

> **Goal:** Understand correlation, why it was invented, and how AI
> engineers use it to measure relationships between variables.

------------------------------------------------------------------------

# Estimated Reading Time

80--90 Minutes

# Difficulty

⭐⭐⭐☆☆

# Prerequisites

-   Lessons 13--31

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson you will be able to:

-   Explain correlation intuitively.
-   Distinguish correlation from covariance.
-   Interpret correlation values.
-   Understand Pearson correlation.
-   Use correlation for feature selection.

------------------------------------------------------------------------

# 1. Why Was Correlation Invented?

Covariance tells us whether two variables move together.

But it has a problem.

Its value depends on the units used.

Example:

``` text
Height (cm)

Weight (kg)
```

versus

``` text
Height (m)

Weight (kg)
```

The covariance changes.

Mathematicians created **correlation** to measure relationships on a
standard scale.

------------------------------------------------------------------------

# 2. Child Analogy

Imagine two friends riding bicycles.

``` text
Friend A speeds up.

↓

Friend B also speeds up.
```

They move together.

Now imagine a see-saw.

``` text
Friend A goes up.

↓

Friend B goes down.
```

They move in opposite directions.

Correlation measures how strongly they move together.

------------------------------------------------------------------------

# 3. Definition

Correlation measures the **strength and direction** of the relationship
between two variables.

Unlike covariance, correlation is always between:

``` text
-1 --------------- 0 --------------- +1
```

------------------------------------------------------------------------

# 4. Correlation Values

``` text
+1  Perfect Positive

0   No Linear Relationship

-1  Perfect Negative
```

------------------------------------------------------------------------

# 5. Positive Correlation

``` text
Study Hours ↑

Marks ↑
```

Scatter Plot

``` text
*
  *
    *
      *
```

------------------------------------------------------------------------

# 6. Negative Correlation

``` text
Exercise ↑

Body Fat ↓
```

Scatter Plot

``` text
      *
    *
  *
*
```

------------------------------------------------------------------------

# 7. Zero Correlation

``` text
Shoe Size

Exam Marks
```

No meaningful linear relationship.

------------------------------------------------------------------------

# 8. Pearson Correlation Coefficient

The most common correlation measure.

Represented by:

``` text
r
```

Interpretation:

``` text
0.90 → Very Strong

0.60 → Moderate

0.20 → Weak
```

The sign (+/-) shows direction.

------------------------------------------------------------------------

# 9. Correlation vs Covariance

``` text
Covariance

✔ Direction

✘ Standardized

Correlation

✔ Direction

✔ Strength

✔ Standardized
```

------------------------------------------------------------------------

# 10. Why AI Uses Correlation

Before training a model:

``` text
Dataset
   │
   ▼
Correlation Matrix
   │
   ▼
Important Features
```

Engineers remove highly redundant features to improve efficiency.

------------------------------------------------------------------------

# 11. Correlation Matrix

``` text
          Age Height Weight

Age      1.00

Height   0.12 1.00

Weight   0.08 0.74 1.00
```

The diagonal is always 1 because a feature is perfectly correlated with
itself.

------------------------------------------------------------------------

# 12. AI Applications

-   Feature Selection
-   Exploratory Data Analysis (EDA)
-   Multicollinearity Detection
-   Healthcare
-   Finance
-   Recommendation Systems

------------------------------------------------------------------------

# 13. Correlation ≠ Causation

``` text
Ice Cream Sales ↑

Sunburn Cases ↑
```

They are correlated.

Ice cream does not cause sunburn.

Hot weather influences both.

Always ask whether a hidden factor exists.

------------------------------------------------------------------------

# 14. Python Example

``` python
import numpy as np

x = [2,4,6,8]
y = [3,5,7,9]

print(np.corrcoef(x, y))
```

------------------------------------------------------------------------

# 15. Pandas Example

``` python
import pandas as pd

df = pd.DataFrame({
    "StudyHours":[2,4,6,8],
    "Marks":[50,65,80,95]
})

print(df.corr())
```

------------------------------------------------------------------------

# 16. Common Mistakes

❌ Correlation proves causation.

❌ Ignoring negative correlation.

❌ Keeping highly correlated duplicate features.

------------------------------------------------------------------------

# 17. Interview Questions

### Basic

What is correlation?

A standardized measure of the strength and direction of a relationship
between two variables.

### Intermediate

Why is correlation preferred over covariance?

Because it is standardized and easier to compare across datasets.

### Advanced

How is correlation used in machine learning?

It helps select useful features, detect redundancy, and understand
relationships before training models.

------------------------------------------------------------------------

# 18. Quick Revision

``` text
Two Variables
      │
      ▼
Correlation
      │
 ┌────┼────┐
 │    │    │
 +    0    -
 │
 ▼
Feature Selection
      │
      ▼
Machine Learning
```

------------------------------------------------------------------------

# Lesson Summary

-   Correlation measures both the strength and direction of a
    relationship.
-   Values range from -1 to +1.
-   Correlation is standardized, unlike covariance.
-   Correlation is widely used in feature engineering and exploratory
    data analysis.
-   Correlation does not imply causation.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 33

Hypothesis Testing

↓

Making Data-Driven Decisions with Confidence
```
