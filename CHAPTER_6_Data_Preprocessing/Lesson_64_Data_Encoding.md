# Chapter 5 – Data Preprocessing

# Lesson 64 – Data Encoding

> **Machine Learning algorithms work with numbers, not words. Data encoding converts categorical information into numerical values that models can understand.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what data encoding is.
- Learn why encoding is necessary.
- Distinguish between categorical data types.
- Explore different encoding techniques.
- Know when each encoding method should be used.
- Prepare for interview questions.

---

# Table of Contents

1. What is Data Encoding?
2. Why Data Encoding is Needed
3. Types of Categorical Data
4. Encoding Techniques
5. Label Encoding
6. One-Hot Encoding
7. Ordinal Encoding
8. Binary Encoding
9. Choosing the Right Encoding
10. Encoding with Pandas & Scikit-Learn
11. Common Mistakes
12. Real-World AI Applications
13. Mini Project
14. Interview Questions
15. Summary
16. What's Next?

---

# 1. What is Data Encoding?

Data encoding is the process of converting categorical (text) values into numerical values that machine learning algorithms can process.

Example:

| Color |
|-------|
| Red |
| Blue |
| Green |

becomes

```
0
1
2
```

or

```
Red   → 1 0 0
Blue  → 0 1 0
Green → 0 0 1
```

---

# 2. Why Data Encoding is Needed

Most ML algorithms perform mathematical operations.

They cannot calculate with text.

```
Model

Input:
"Red"

❌ Cannot Compute

↓

Encoded Value

↓

Model Can Learn
```

---

# 3. Types of Categorical Data

## Nominal Data

No natural order.

Examples:

- Red
- Blue
- Green

- India
- Japan
- Brazil

---

## Ordinal Data

Has a meaningful order.

Examples:

- Small
- Medium
- Large

or

- Poor
- Average
- Good
- Excellent

---

# 4. Encoding Techniques

Common methods:

- Label Encoding
- One-Hot Encoding
- Ordinal Encoding
- Binary Encoding
- Target Encoding (advanced)

Each technique is suitable for different situations.

---

# 5. Label Encoding

Each category gets a unique integer.

Example:

```
Cat → 0
Dog → 1
Bird → 2
```

Python:

```python
from sklearn.preprocessing import LabelEncoder

encoder = LabelEncoder()

df["Animal"] = encoder.fit_transform(df["Animal"])
```

Simple and memory efficient.

---

# 6. One-Hot Encoding

Creates one column for every category.

Example:

| Color | Red | Blue | Green |
|------|----|-----|------|
| Red |1|0|0|
| Blue|0|1|0|
| Green|0|0|1|

Python:

```python
pd.get_dummies(df["Color"])
```

or

```python
from sklearn.preprocessing import OneHotEncoder
```

---

# 7. Ordinal Encoding

Used when categories have a logical order.

Example:

```
Small  → 1
Medium → 2
Large  → 3
```

Python:

```python
from sklearn.preprocessing import OrdinalEncoder
```

---

# 8. Binary Encoding

Large numbers of categories can create many columns.

Binary encoding converts category IDs into binary values.

Useful for high-cardinality features.

---

# 9. Choosing the Right Encoding

| Data Type | Recommended Encoding |
|-----------|----------------------|
| Nominal | One-Hot Encoding |
| Ordinal | Ordinal Encoding |
| Few categories | Label Encoding |
| Many categories | Binary / Target Encoding |

---

# 10. Encoding with Pandas & Scikit-Learn

Using Pandas:

```python
pd.get_dummies(df, columns=["City"])
```

Using Scikit-Learn:

```python
from sklearn.preprocessing import OneHotEncoder

encoder = OneHotEncoder()

encoded = encoder.fit_transform(df[["City"]])
```

---

# 11. Common Mistakes

- Using Label Encoding for nominal data.
- Forgetting to encode categorical variables.
- Creating too many columns with one-hot encoding.
- Fitting encoders separately on train and test data.

---

# 12. Real-World AI Applications

```
Customer Data

Gender
City
Education
Occupation

        │

Encoding

        │

Machine Learning Model

        │

Prediction
```

Applications:

- Credit scoring
- Customer segmentation
- Fraud detection
- Recommendation systems

---

# 13. Mini Project

Using a customer dataset:

1. Identify categorical columns.
2. Apply Label Encoding where appropriate.
3. Apply One-Hot Encoding for nominal features.
4. Compare the transformed dataset.
5. Save the encoded dataset.

---

# 14. Interview Questions

### What is data encoding?

Converting categorical values into numerical values for machine learning.

### Why can't ML models use text directly?

Most algorithms perform mathematical calculations and require numeric input.

### When should One-Hot Encoding be used?

For nominal categorical variables without any natural order.

### When is Label Encoding appropriate?

When categories have a meaningful order or for target labels.

### What is the disadvantage of One-Hot Encoding?

It increases the number of features, especially with many categories.

---

# 15. Summary

You learned:

- Why encoding is required.
- Nominal vs ordinal data.
- Label Encoding.
- One-Hot Encoding.
- Ordinal Encoding.
- Binary Encoding.
- Choosing the correct technique.
- Common mistakes.

---

# 16. What's Next?

**Lesson 65 – Label Encoding**

You'll study Label Encoding in depth, understand its internal working, advantages, limitations, and when it should and should not be used in machine learning projects.
