# Chapter 5 – Data Preprocessing

# Lesson 62 – Duplicate Data

> **Duplicate data silently corrupts analysis and machine learning models. Detecting and removing duplicates is a fundamental preprocessing task.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what duplicate data is.
- Learn why duplicate records occur.
- Identify exact and partial duplicates.
- Detect duplicates using Pandas.
- Remove duplicates safely.
- Understand the impact of duplicates on AI models.
- Prepare for interview questions.

---

# Table of Contents

1. What is Duplicate Data?
2. Why Duplicates Occur
3. Types of Duplicates
4. Why Duplicate Data is Harmful
5. Detecting Duplicates
6. Removing Duplicates
7. Keeping the Correct Record
8. Best Practices
9. Real-World Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

---

# 1. What is Duplicate Data?

Duplicate data refers to records that appear more than once in a dataset.

Example:

| ID | Name | City |
|----|------|------|
|101|Alice|Pune|
|102|Bob|Mumbai|
|102|Bob|Mumbai|

The second and third rows are duplicates.

---

# 2. Why Duplicates Occur

Common causes:

- Manual data entry
- Importing the same file multiple times
- System synchronization errors
- Data migration
- Multiple users entering the same information
- Web scraping repeated pages

---

# 3. Types of Duplicates

## Exact Duplicates

Every value is identical.

```
101 Alice Pune
101 Alice Pune
```

## Partial Duplicates

Some fields differ.

```
Alice   Pune
Alice   Pune City
```

These often require domain knowledge to resolve.

---

# 4. Why Duplicate Data is Harmful

```
Duplicate Records
        │
        ▼
Biased Statistics
        │
        ▼
Incorrect ML Training
        │
        ▼
Poor Predictions
```

Problems include:

- Inflated dataset size
- Incorrect averages
- Biased models
- Wasted storage
- Slower processing

---

# 5. Detecting Duplicates

Load data:

```python
import pandas as pd

df = pd.read_csv("students.csv")
```

Find duplicates:

```python
df.duplicated()
```

Count duplicates:

```python
df.duplicated().sum()
```

Display duplicate rows:

```python
df[df.duplicated()]
```

Check duplicates based on specific columns:

```python
df.duplicated(subset=["Name", "City"])
```

---

# 6. Removing Duplicates

Remove duplicate rows:

```python
df = df.drop_duplicates()
```

Keep first occurrence:

```python
df.drop_duplicates(keep="first")
```

Keep last occurrence:

```python
df.drop_duplicates(keep="last")
```

Remove every duplicated record:

```python
df.drop_duplicates(keep=False)
```

---

# 7. Keeping the Correct Record

Sometimes duplicates contain updated information.

Example:

| ID | Salary |
|----|--------|
|101|50000|
|101|55000|

Business rules decide which record should remain.

Possible strategies:

- Keep latest record
- Keep highest quality record
- Merge information
- Ask domain experts

---

# 8. Best Practices

- Investigate before deleting.
- Backup original data.
- Use unique identifiers.
- Check duplicates after merging datasets.
- Validate the cleaned dataset.

---

# 9. Real-World Example

Customer database:

Before:

```
Alice
Alice
Bob
Bob
Charlie
```

After removing duplicates:

```
Alice
Bob
Charlie
```

The cleaned dataset produces more reliable reports and models.

---

# 10. Mini Project

Using a CSV dataset:

1. Count duplicate rows.
2. Display all duplicates.
3. Remove duplicates.
4. Compare dataset size before and after cleaning.
5. Save the cleaned dataset.

---

# 11. Interview Questions

### What is duplicate data?

Repeated records representing the same information.

### Which Pandas function detects duplicates?

```python
duplicated()
```

### Which function removes duplicates?

```python
drop_duplicates()
```

### Why are duplicate records harmful?

They bias statistics, increase storage, and reduce model quality.

### What is the difference between exact and partial duplicates?

- Exact duplicates have identical values.
- Partial duplicates differ in some fields but may represent the same entity.

---

# 12. Summary

You learned:

- What duplicate data is.
- Causes of duplicate records.
- Exact vs partial duplicates.
- Detecting duplicates.
- Removing duplicates.
- Best practices.
- Real-world applications.

---

# 13. What's Next?

**Lesson 63 – Outliers**

You'll learn how unusual data points influence machine learning models, methods for detecting outliers, and techniques for handling them using statistical and visualization approaches.
