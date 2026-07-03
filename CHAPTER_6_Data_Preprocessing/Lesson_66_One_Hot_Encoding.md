# Chapter 5 – Data Preprocessing

# Lesson 66 – One-Hot Encoding

> **One-Hot Encoding is one of the most important preprocessing techniques in Machine Learning. It converts categorical values into binary vectors without introducing an artificial numerical order.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what One-Hot Encoding is.
- Learn why it was invented.
- Understand its internal working.
- Compare it with Label Encoding.
- Use One-Hot Encoding with Pandas and Scikit-Learn.
- Learn about dummy variables and sparse matrices.
- Prepare for interview questions.

---

# Table of Contents

1. What is One-Hot Encoding?
2. Why One-Hot Encoding was Invented
3. How One-Hot Encoding Works
4. Label Encoding vs One-Hot Encoding
5. Dummy Variables
6. Dummy Variable Trap
7. Pandas Implementation
8. Scikit-Learn Implementation
9. Sparse Matrices
10. Advantages
11. Limitations
12. Real-World Applications
13. Common Mistakes
14. Mini Project
15. Interview Questions
16. Summary
17. What's Next?

---

# 1. What is One-Hot Encoding?

One-Hot Encoding converts every category into a separate binary feature.

Example:

| Color |
|-------|
| Red |
| Blue |
| Green |

becomes

| Red | Blue | Green |
|----|----|----|
|1|0|0|
|0|1|0|
|0|0|1|

Each category receives its own column.

---

# 2. Why One-Hot Encoding was Invented

Label Encoding assigns numbers:

```
Red → 0
Blue → 1
Green → 2
```

Some algorithms mistakenly assume:

```
Green > Blue > Red
```

This relationship does not exist.

One-Hot Encoding removes this false ordering.

---

# 3. How One-Hot Encoding Works

```
Original Column

City

Pune
Delhi
Mumbai

        │

Create New Columns

Pune Delhi Mumbai

        │

Binary Representation

1 0 0

0 1 0

0 0 1
```

---

# 4. Label Encoding vs One-Hot Encoding

| Feature | Label Encoding | One-Hot Encoding |
|---------|----------------|------------------|
| Output | Integer | Binary Columns |
| Artificial Order | Yes | No |
| Memory Usage | Low | Higher |
| Best For | Ordinal Data | Nominal Data |

---

# 5. Dummy Variables

Each binary column is called a **dummy variable**.

Example:

```
Fruit

Apple
Banana
Orange
```

becomes

```
Apple Banana Orange

1      0      0

0      1      0

0      0      1
```

---

# 6. Dummy Variable Trap

If all dummy columns are kept, one column can often be predicted from the others.

Example:

```
Red Blue Green

1   0    0
0   1    0
0   0    1
```

Removing one column avoids redundant information.

In Pandas:

```python
pd.get_dummies(df, drop_first=True)
```

---

# 7. Pandas Implementation

```python
import pandas as pd

df = pd.DataFrame({
    "City": ["Pune", "Delhi", "Mumbai"]
})

encoded = pd.get_dummies(df, columns=["City"])

print(encoded)
```

---

# 8. Scikit-Learn Implementation

```python
from sklearn.preprocessing import OneHotEncoder

encoder = OneHotEncoder()

encoded = encoder.fit_transform(df[["City"]])
```

Convert to an array:

```python
encoded.toarray()
```

---

# 9. Sparse Matrices

One-Hot Encoding creates many zeros.

Instead of storing every zero, Scikit-Learn stores only important values.

```
Normal Matrix

1 0 0
0 1 0
0 0 1

↓

Sparse Matrix

Stores only:

(0,0)=1
(1,1)=1
(2,2)=1
```

This saves memory.

---

# 10. Advantages

- Removes artificial ordering.
- Works well with nominal data.
- Easy to understand.
- Supported by almost every ML library.
- Widely used in production pipelines.

---

# 11. Limitations

- Creates many new columns.
- High-cardinality features increase memory usage.
- May slow model training for very large datasets.

---

# 12. Real-World Applications

Examples:

- Customer city
- Product category
- Browser type
- Payment method
- Department
- Vehicle type

Pipeline

```
Raw Categories
      │
      ▼
One-Hot Encoding
      │
      ▼
Machine Learning Model
```

---

# 13. Common Mistakes

- Using One-Hot Encoding on ordinal data.
- Applying encoding separately to training and test data.
- Forgetting about the dummy variable trap.
- One-hot encoding extremely high-cardinality features.

---

# 14. Mini Project

Using a customer dataset:

1. Identify nominal columns.
2. Apply `pd.get_dummies()`.
3. Apply `drop_first=True`.
4. Compare dataset size before and after encoding.
5. Save the encoded dataset.

---

# 15. Interview Questions

### What is One-Hot Encoding?

A preprocessing technique that converts categorical variables into binary columns.

### Why is it preferred over Label Encoding?

Because it avoids introducing artificial numerical order.

### What is the dummy variable trap?

A situation where dummy variables become perfectly correlated, introducing redundancy.

### Which Pandas function performs One-Hot Encoding?

```python
pd.get_dummies()
```

### Why are sparse matrices useful?

They reduce memory usage by storing only non-zero values.

---

# 16. Summary

You learned:

- Why One-Hot Encoding exists.
- Internal working.
- Dummy variables.
- Dummy variable trap.
- Pandas and Scikit-Learn implementations.
- Advantages and limitations.
- Real-world use cases.

---

# 17. What's Next?

**Lesson 67 – Feature Scaling**

You'll learn why features with different ranges confuse machine learning algorithms and how scaling techniques improve model performance.
