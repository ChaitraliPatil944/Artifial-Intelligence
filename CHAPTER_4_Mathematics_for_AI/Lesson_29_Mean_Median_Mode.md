# Lesson 29: Mean, Median & Mode

## Part III -- Mathematics for AI

> **Goal:** Understand the three measures of central tendency, why they
> were invented, and how AI engineers use them to summarize data.

------------------------------------------------------------------------

# Estimated Reading Time

75--90 Minutes

# Difficulty

⭐⭐⭐☆☆

# Prerequisites

-   Lessons 13--28

------------------------------------------------------------------------

# Learning Objectives

By the end of this lesson you will be able to:

-   Explain mean, median, and mode.
-   Choose the correct measure for different datasets.
-   Understand the effect of outliers.
-   Apply these concepts during data preprocessing.
-   Use Python to calculate them.

------------------------------------------------------------------------

# 1. Why Were Mean, Median & Mode Invented?

Imagine a teacher has marks for 5,000 students.

Instead of reading every mark, the teacher wants one number that
represents the class.

These measures summarize the "center" of the data.

``` text
Thousands of Values
        │
        ▼
Single Representative Number
```

------------------------------------------------------------------------

# 2. Child Analogy

Imagine five children have chocolates.

``` text
2  3  4  5  6
```

Instead of remembering every number, you ask:

> "What is the typical number of chocolates?"

That is the purpose of central tendency.

------------------------------------------------------------------------

# 3. Mean (Average)

The mean is the sum of all values divided by the number of values.

Formula:

``` text
Mean = Sum of Values / Number of Values
```

Example:

``` text
Marks

70 80 90

Mean

= (70+80+90)/3

= 80
```

------------------------------------------------------------------------

# 4. Median

The median is the middle value after sorting.

Example:

``` text
10 20 30 40 50

Median = 30
```

Even number of values:

``` text
10 20 30 40

Median = (20+30)/2 = 25
```

------------------------------------------------------------------------

# 5. Mode

The mode is the value that appears most often.

Example:

``` text
2 2 3 4 5

Mode = 2
```

A dataset may have:

-   No mode
-   One mode
-   Multiple modes

------------------------------------------------------------------------

# 6. Comparing Them

``` text
Mean   → Arithmetic Average

Median → Middle Value

Mode   → Most Frequent Value
```

------------------------------------------------------------------------

# 7. Effect of Outliers

Dataset:

``` text
10 12 13 15 200
```

Mean:

``` text
50
```

Median:

``` text
13
```

The value **200** pulls the mean upward.

The median remains stable.

------------------------------------------------------------------------

# 8. When Should You Use Each?

  Situation              Best Measure
  ---------------------- --------------
  Symmetric data         Mean
  Data with outliers     Median
  Most common category   Mode

------------------------------------------------------------------------

# 9. Why AI Uses Them

Before training a model, AI engineers summarize features.

``` text
Raw Data
    │
    ▼
Mean
Median
Mode
    │
    ▼
Understand Data
```

------------------------------------------------------------------------

# 10. AI Applications

## Missing Value Imputation

``` text
Missing Age

↓

Replace with Mean

or

Median
```

------------------------------------------------------------------------

## Customer Analytics

``` text
Purchase Amounts

↓

Median Spending
```

------------------------------------------------------------------------

## Recommendation Systems

Mode can identify the most popular products.

------------------------------------------------------------------------

# 11. Python Example

``` python
import statistics

marks = [70,75,80,82,90]

print(statistics.mean(marks))
print(statistics.median(marks))
print(statistics.mode(marks))
```

------------------------------------------------------------------------

# 12. Pandas Example

``` python
import pandas as pd

df = pd.DataFrame({"Marks":[70,75,80,82,90]})

print(df.mean())
print(df.median())
print(df.mode())
```

------------------------------------------------------------------------

# 13. Common Mistakes

❌ Using the mean when extreme outliers exist.

❌ Assuming mode always exists.

❌ Forgetting to sort data before finding the median.

------------------------------------------------------------------------

# 14. Interview Questions

### Basic

What is the difference between mean, median, and mode?

Mean is the average, median is the middle value, and mode is the most
frequent value.

### Intermediate

Why is the median preferred when outliers are present?

Because it is less affected by extreme values.

### Advanced

How are these measures used in machine learning?

They summarize data, detect skewness, and help fill missing values
during preprocessing.

------------------------------------------------------------------------

# 15. Quick Revision

``` text
Dataset
   │
   ├── Mean
   ├── Median
   └── Mode
        │
        ▼
Data Understanding
        │
        ▼
Machine Learning
```

------------------------------------------------------------------------

# Lesson Summary

-   Mean is the arithmetic average.
-   Median is the middle value.
-   Mode is the most frequent value.
-   Outliers mainly affect the mean.
-   AI engineers use these measures during exploratory data analysis and
    preprocessing.

------------------------------------------------------------------------

# Next Lesson

``` text
Lesson 30

Variance & Standard Deviation

↓

Measuring How Spread Out Data Is
```
