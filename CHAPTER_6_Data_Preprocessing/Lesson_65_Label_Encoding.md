# Chapter 5 – Data Preprocessing

# Lesson 65 – Label Encoding

> **Label Encoding is one of the simplest techniques for converting categorical data into numbers. Understanding when to use it and when to avoid it is crucial for building accurate machine learning models.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Label Encoding is.
- Learn why it was introduced.
- Understand how it works internally.
- Know when Label Encoding should and should not be used.
- Compare Label Encoding with One-Hot Encoding and Ordinal Encoding.
- Implement Label Encoding using Scikit-Learn.
- Prepare for interview questions.

---

# Table of Contents

1. What is Label Encoding?
2. Why Label Encoding Exists
3. How Label Encoding Works
4. Internal Working
5. Advantages
6. Limitations
7. When to Use Label Encoding
8. When NOT to Use Label Encoding
9. Label Encoding vs One-Hot Encoding
10. LabelEncoder vs OrdinalEncoder
11. Python Implementation
12. Real-World Applications
13. Common Mistakes
14. Mini Project
15. Interview Questions
16. Summary
17. What's Next?

---

# 1. What is Label Encoding?

Label Encoding converts each unique category into an integer.

Example:

| Animal | Encoded |
|---------|---------|
| Cat | 0 |
| Dog | 1 |
| Bird | 2 |

Every category receives a unique numeric label.

---

# 2. Why Label Encoding Exists

Machine learning algorithms cannot perform mathematical operations on text.

Instead of:

```
Apple
Orange
Banana
```

we convert them into

```
0
1
2
```

making them suitable for algorithms.

---

# 3. How Label Encoding Works

```
Original Data
     │
     ▼
Find Unique Categories
     │
     ▼
Assign Integer Labels
     │
     ▼
Encoded Dataset
```

Example:

```
Small
Medium
Large
```

becomes

```
0
1
2
```

---

# 4. Internal Working

Scikit-Learn sorts unique categories alphabetically before assigning labels.

Example:

```
Apple
Banana
Orange
```

Encoding:

```
Apple  → 0
Banana → 1
Orange → 2
```

The numbers are identifiers, not measurements.

---

# 5. Advantages

- Simple to implement.
- Fast execution.
- Memory efficient.
- Works well for target labels.
- Suitable for ordered categories.

---

# 6. Limitations

The biggest limitation is that Label Encoding introduces an artificial numerical order.

Example:

```
Red   → 0
Blue  → 1
Green → 2
```

A model may incorrectly assume:

```
Green > Blue > Red
```

even though colors have no natural ranking.

---

# 7. When to Use Label Encoding

Recommended for:

- Target labels (classification output)
- Ordinal categories
- Tree-based algorithms (Decision Trees, Random Forests) where artificial order is less problematic.

Examples:

```
Poor
Average
Good
Excellent
```

---

# 8. When NOT to Use Label Encoding

Avoid for nominal variables such as:

- City
- Country
- Color
- Department

Instead, use One-Hot Encoding.

---

# 9. Label Encoding vs One-Hot Encoding

| Feature | Label Encoding | One-Hot Encoding |
|---------|----------------|------------------|
| Output | Integers | Binary Columns |
| Memory | Low | Higher |
| Suitable for Nominal | ❌ | ✅ |
| Suitable for Ordinal | ✅ | Possible |
| High Cardinality | Better | Can create many columns |

---

# 10. LabelEncoder vs OrdinalEncoder

| LabelEncoder | OrdinalEncoder |
|--------------|----------------|
| Encodes target labels | Encodes input features |
| One-dimensional | Multiple columns |
| Used mainly for y | Used for X |

---

# 11. Python Implementation

```python
from sklearn.preprocessing import LabelEncoder

import pandas as pd

df = pd.DataFrame({
    "Size": ["Small", "Medium", "Large", "Medium"]
})

encoder = LabelEncoder()

df["Encoded"] = encoder.fit_transform(df["Size"])

print(df)
```

Decode back:

```python
encoder.inverse_transform(df["Encoded"])
```

---

# 12. Real-World Applications

Examples:

- Sentiment Analysis

```
Positive → 2
Neutral  → 1
Negative → 0
```

- Email Classification
- Disease Categories
- Product Ratings

Pipeline:

```
Raw Categories
      │
      ▼
Label Encoding
      │
      ▼
Machine Learning Model
```

---

# 13. Common Mistakes

- Using Label Encoding for nominal variables.
- Forgetting to save the fitted encoder.
- Fitting separate encoders on training and test datasets.
- Assuming encoded numbers have mathematical meaning.

---

# 14. Mini Project

Using a customer dataset:

1. Identify an ordinal column.
2. Apply Label Encoding.
3. Display original and encoded values.
4. Decode the values using `inverse_transform()`.
5. Explain whether Label Encoding is appropriate.

---

# 15. Interview Questions

### What is Label Encoding?

A preprocessing technique that converts categorical values into unique integers.

### Why is Label Encoding not suitable for nominal data?

Because it introduces an artificial order that does not actually exist.

### Which Scikit-Learn class performs Label Encoding?

```python
from sklearn.preprocessing import LabelEncoder
```

### Difference between LabelEncoder and OrdinalEncoder?

LabelEncoder is mainly used for target labels, whereas OrdinalEncoder is used for input features.

### Can encoded values be converted back?

Yes, using:

```python
inverse_transform()
```

---

# 16. Summary

You learned:

- What Label Encoding is.
- Why it was introduced.
- Internal working.
- Advantages and disadvantages.
- Proper use cases.
- Python implementation.
- Common mistakes.
- Real-world applications.

---

# 17. What's Next?

**Lesson 66 – One-Hot Encoding**

You'll learn one of the most important preprocessing techniques in machine learning, why it avoids artificial ordering, and when it is preferred over Label Encoding.
