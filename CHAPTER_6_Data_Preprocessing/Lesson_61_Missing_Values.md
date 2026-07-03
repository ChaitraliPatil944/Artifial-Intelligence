# Chapter 5 – Data Preprocessing

# Lesson 61 – Missing Values

> **Missing data is one of the most common problems in Machine Learning. Handling it correctly can dramatically improve model performance and reliability.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what missing values are.
- Learn why missing values occur.
- Explore different types of missing data.
- Detect missing values using Pandas.
- Apply common techniques to handle missing values.
- Understand the impact of missing data on Machine Learning models.
- Prepare for interview questions.

---

# Table of Contents

1. What are Missing Values?
2. Why Missing Values Occur
3. Types of Missing Data
4. Detecting Missing Values
5. Removing Missing Values
6. Filling Missing Values (Imputation)
7. Advanced Imputation Techniques
8. Choosing the Right Strategy
9. Impact on Machine Learning
10. Best Practices
11. Real-World Example
12. Mini Project
13. Interview Questions
14. Summary
15. What's Next?

---

# 1. What are Missing Values?

Missing values are pieces of information that are absent from a dataset.

Example:

| Name | Age | Salary |
|------|-----|--------|
| Alice | 24 | 45000 |
| Bob | NaN | 52000 |
| Carol | 28 | NaN |

`NaN` means **Not a Number**, which Pandas uses to represent missing values.

---

# 2. Why Missing Values Occur

Common reasons include:

- Human error
- Survey respondents skipping questions
- Sensor failures
- Data corruption
- Database migration issues
- Privacy restrictions

Missing values are normal in real-world datasets.

---

# 3. Types of Missing Data

### MCAR (Missing Completely At Random)

Missing values occur randomly.

Example:

```
Age
23
NaN
41
18
```

### MAR (Missing At Random)

Missing values depend on another variable.

Example:

Older customers are less likely to provide income information.

### MNAR (Missing Not At Random)

Missing values depend on the missing value itself.

Example:

People with very high salaries choose not to disclose them.

---

# 4. Detecting Missing Values

Load a dataset:

```python
import pandas as pd

df = pd.read_csv("students.csv")
```

Check missing values:

```python
df.isnull()
```

Count them:

```python
df.isnull().sum()
```

Percentage:

```python
(df.isnull().sum() / len(df)) * 100
```

---

# 5. Removing Missing Values

Remove rows with missing values:

```python
df.dropna()
```

Remove columns with missing values:

```python
df.dropna(axis=1)
```

Only remove rows where every value is missing:

```python
df.dropna(how="all")
```

Use this carefully because valuable data may be lost.

---

# 6. Filling Missing Values (Imputation)

Replace with a constant:

```python
df.fillna(0)
```

Mean:

```python
df["Age"].fillna(df["Age"].mean(), inplace=True)
```

Median:

```python
df["Age"].fillna(df["Age"].median(), inplace=True)
```

Mode:

```python
df["City"].fillna(df["City"].mode()[0], inplace=True)
```

Forward Fill:

```python
df.fillna(method="ffill")
```

Backward Fill:

```python
df.fillna(method="bfill")
```

---

# 7. Advanced Imputation Techniques

Machine Learning often uses:

- KNN Imputer
- Iterative Imputer
- Regression-based imputation

Example:

```python
from sklearn.impute import KNNImputer

imputer = KNNImputer(n_neighbors=3)
```

These methods estimate missing values using existing data.

---

# 8. Choosing the Right Strategy

| Situation | Recommended Method |
|-----------|--------------------|
| Few missing rows | Drop rows |
| Numerical feature | Mean or Median |
| Categorical feature | Mode |
| Time-series | Forward/Backward Fill |
| Complex dataset | KNN or Iterative Imputer |

---

# 9. Impact on Machine Learning

```
Raw Data
   │
   ▼
Missing Values
   │
   ▼
Imputation
   │
   ▼
Model Training
```

Ignoring missing values can:

- Reduce accuracy
- Introduce bias
- Cause algorithms to fail

---

# 10. Best Practices

- Understand why values are missing.
- Avoid blindly replacing values.
- Prefer median for skewed numerical data.
- Document every preprocessing step.
- Validate results after imputation.

---

# 11. Real-World Example

Hospital Dataset:

```
Patient   Blood Pressure
A         120
B         NaN
C         135
```

Instead of deleting Patient B, replace the missing value using the median blood pressure so valuable patient information is retained.

---

# 12. Mini Project

Using any CSV dataset:

1. Count missing values.
2. Calculate missing percentages.
3. Fill numerical columns with the median.
4. Fill categorical columns with the mode.
5. Save the cleaned dataset.

---

# 13. Interview Questions

### What are missing values?

Missing or unavailable information in a dataset.

### What does NaN stand for?

Not a Number.

### Difference between Mean and Median imputation?

- Mean is affected by outliers.
- Median is more robust for skewed data.

### What is MCAR?

Missing Completely At Random.

### When should rows be removed?

When only a small number of records are missing and removing them does not significantly reduce the dataset.

---

# 14. Summary

You learned:

- What missing values are.
- Why they occur.
- MCAR, MAR and MNAR.
- Detecting missing values.
- Dropping vs imputing.
- Mean, Median, Mode, Forward Fill and KNN imputation.
- Best practices for preprocessing.

---

# 15. What's Next?

**Lesson 62 – Duplicate Data**

You'll learn how duplicate records appear, why they are harmful, how to detect them efficiently, and how AI engineers remove them before model training.
