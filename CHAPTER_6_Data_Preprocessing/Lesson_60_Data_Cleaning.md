# Chapter 5 – Data Preprocessing

# Lesson 60 – Data Cleaning

> **Real-world data is messy. Data cleaning transforms raw, unreliable data into a trustworthy foundation for Machine Learning.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what data cleaning is.
- Learn why it is one of the most important steps in AI.
- Identify common data quality problems.
- Clean datasets using Pandas.
- Understand the real-world data cleaning workflow.
- Prepare for interview questions.

---

# Table of Contents

1. What is Data Cleaning?
2. Why Data Cleaning Matters
3. Common Data Quality Problems
4. Data Cleaning Workflow
5. Detecting Errors
6. Removing Invalid Data
7. Standardizing Data
8. Cleaning with Pandas
9. Best Practices
10. Real-World Example
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

---

# 1. What is Data Cleaning?

Data cleaning is the process of finding and correcting errors, inconsistencies, duplicates, and invalid values in a dataset.

Raw data is rarely perfect.

---

# 2. Why Data Cleaning Matters

Machine learning models learn from data.

```
Raw Data
    │
    ▼
Dirty Data
    │
    ▼
Poor Model

Clean Data
    │
    ▼
Reliable Model
```

Even the best algorithm cannot compensate for poor-quality data.

---

# 3. Common Data Quality Problems

Examples include:

- Missing values
- Duplicate records
- Typographical errors
- Incorrect formats
- Outliers
- Inconsistent labels
- Invalid entries

Example:

```
Age
23
25
-10
200
NULL
```

Clearly, not every value is valid.

---

# 4. Data Cleaning Workflow

```
Collect Data
      │
      ▼
Inspect Dataset
      │
      ▼
Detect Errors
      │
      ▼
Clean Data
      │
      ▼
Validate
      │
      ▼
Model Training
```

---

# 5. Detecting Errors

Useful Pandas commands:

```python
import pandas as pd

df = pd.read_csv("students.csv")

df.info()

df.describe()

df.isnull().sum()

df.duplicated().sum()
```

These provide a quick overview of data quality.

---

# 6. Removing Invalid Data

Example:

```python
df = df[df["Age"] >= 0]

df = df[df["Marks"] <= 100]
```

Business rules help identify impossible values.

---

# 7. Standardizing Data

Inconsistent entries:

```
Male
male
MALE
M
```

Standardize them:

```python
df["Gender"] = df["Gender"].str.lower()
```

Consistent formatting improves analysis.

---

# 8. Cleaning with Pandas

Remove duplicates:

```python
df = df.drop_duplicates()
```

Rename columns:

```python
df.columns = df.columns.str.strip()
```

Replace values:

```python
df["City"] = df["City"].replace("Bombay", "Mumbai")
```

Convert data types:

```python
df["Age"] = df["Age"].astype(int)
```

---

# 9. Best Practices

- Understand the dataset before cleaning.
- Never delete data without a reason.
- Keep a copy of the original dataset.
- Document every cleaning step.
- Validate the cleaned dataset.

---

# 10. Real-World Example

E-commerce customer data:

Before cleaning:

```
Name      City
Alice     Pune
Alice     Pune
Bob       MUMBAI
Charlie   NULL
```

After cleaning:

```
Name      City
Alice     Pune
Bob       Mumbai
Charlie   Unknown
```

The cleaned dataset is now suitable for analytics and machine learning.

---

# 11. Mini Project

Using a CSV dataset:

1. Identify missing values.
2. Remove duplicate rows.
3. Standardize text values.
4. Correct invalid numerical values.
5. Save the cleaned dataset as `cleaned_data.csv`.

---

# 12. Interview Questions

### What is data cleaning?

The process of detecting and correcting inaccurate, incomplete, duplicate, or inconsistent data.

### Why is data cleaning important?

Because model quality depends heavily on data quality.

### Which Pandas function removes duplicate rows?

```python
drop_duplicates()
```

### Why should you keep the original dataset?

To avoid permanent data loss and allow reproducibility.

---

# 13. Summary

You learned:

- What data cleaning is.
- Common data quality issues.
- Cleaning workflow.
- Detecting errors.
- Standardizing values.
- Cleaning data using Pandas.
- Industry best practices.

---

# 14. What's Next?

**Lesson 61 – Missing Values**

You'll learn why missing data occurs, different types of missing values, and the techniques AI engineers use to handle them without introducing bias into machine learning models.
