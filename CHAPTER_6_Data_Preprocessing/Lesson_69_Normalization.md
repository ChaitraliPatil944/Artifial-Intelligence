# Chapter 5 – Data Preprocessing

# Lesson 69 – Normalization

> **Normalization rescales numerical features to a fixed range, allowing Machine Learning algorithms to compare features fairly and converge more efficiently.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Normalization is.
- Learn why it is needed.
- Understand Min-Max Scaling.
- Learn L1 and L2 Normalization.
- Use Scikit-Learn to normalize data.
- Compare Normalization with Standardization.
- Prepare for interview questions.

---

# Table of Contents

1. What is Normalization?
2. Why Normalization is Needed
3. Min-Max Scaling
4. L1 & L2 Normalization
5. MinMaxScaler
6. Normalizer
7. Standardization vs Normalization
8. Algorithms That Benefit
9. Advantages
10. Limitations
11. Best Practices
12. Real-World Applications
13. Mini Project
14. Interview Questions
15. Summary
16. What's Next?

---

# 1. What is Normalization?

Normalization is a feature scaling technique that transforms values into a fixed range, usually:

```
0 to 1
```

Example:

Before

```
Age
20
35
60
```

After

```
0.00
0.38
1.00
```

---

# 2. Why Normalization is Needed

Consider:

| Feature | Values |
|---------|--------|
| Age | 18–60 |
| Income | 20,000–2,000,000 |

Income dominates distance calculations.

Normalization ensures both contribute fairly.

---

# 3. Min-Max Scaling

The most common normalization technique.

Formula:

```
X' = (X - Min) / (Max - Min)
```

Where:

- X = Original value
- Min = Minimum feature value
- Max = Maximum feature value

Output lies between **0 and 1**.

Example:

Original:

```
10
20
30
40
50
```

Normalized:

```
0.00
0.25
0.50
0.75
1.00
```

---

# 4. L1 & L2 Normalization

Unlike Min-Max Scaling, these normalize each sample.

### L1 Normalization

Sum of absolute values becomes 1.

```
|x1| + |x2| + ... = 1
```

Useful in sparse data.

### L2 Normalization

Length (Euclidean norm) becomes 1.

```
√(x1²+x2²+...) = 1
```

Common in text processing, recommendation systems, and deep learning.

---

# 5. MinMaxScaler

```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()

X_train_scaled = scaler.fit_transform(X_train)

X_test_scaled = scaler.transform(X_test)
```

Default range:

```
0 → 1
```

Custom range:

```python
MinMaxScaler(feature_range=(-1,1))
```

---

# 6. Normalizer

```python
from sklearn.preprocessing import Normalizer

normalizer = Normalizer(norm="l2")

X_normalized = normalizer.fit_transform(X)
```

Options:

- l1
- l2
- max

---

# 7. Standardization vs Normalization

| Standardization | Normalization |
|-----------------|---------------|
| Mean = 0 | Fixed range |
| Std Dev = 1 | Usually 0–1 |
| Uses Z-score | Uses Min-Max |
| Sensitive to outliers | Also affected by outliers |
| Preferred for Gaussian data | Preferred for bounded features |

Quick comparison:

```
Standardization
↓

-2  -1  0  1  2

Normalization
↓

0  0.25  0.5  0.75  1
```

---

# 8. Algorithms That Benefit

Normalization is useful for:

- KNN
- Neural Networks
- K-Means
- SVM
- PCA
- Gradient Descent methods

Distance-based algorithms particularly benefit.

---

# 9. Advantages

- Comparable feature ranges.
- Faster convergence.
- Prevents dominance by large-valued features.
- Improves numerical stability.

---

# 10. Limitations

- Sensitive to extreme values.
- Requires knowing minimum and maximum values.
- New data outside training range may exceed 0–1.

---

# 11. Best Practices

```
Split Data
     │
     ▼
Fit Scaler on Train
     │
     ▼
Transform Train
     │
     ▼
Transform Test
```

Never fit on the complete dataset.

Save the fitted scaler for production use.

---

# 12. Real-World Applications

Examples:

- Image pixel scaling (0–255 → 0–1)
- Customer analytics
- Recommendation engines
- Medical diagnosis
- Credit scoring
- Deep Learning pipelines

---

# 13. Mini Project

Using a customer dataset:

1. Select numerical columns.
2. Apply MinMaxScaler.
3. Plot values before and after scaling.
4. Train a KNN model.
5. Compare performance before and after normalization.

---

# 14. Interview Questions

### What is Normalization?

A preprocessing technique that rescales numerical values to a fixed range, usually 0–1.

### What is the Min-Max formula?

```
(X - Min) / (Max - Min)
```

### Difference between Standardization and Normalization?

Standardization produces zero mean and unit variance.

Normalization rescales values to a bounded range.

### Which Scikit-Learn class performs Min-Max Scaling?

```python
from sklearn.preprocessing import MinMaxScaler
```

### When is Normalization preferred?

When algorithms depend on distances or when features should lie within a fixed range.

---

# 15. Summary

You learned:

- What Normalization is.
- Why it is required.
- Min-Max Scaling.
- L1 and L2 Normalization.
- MinMaxScaler.
- Normalizer.
- Standardization vs Normalization.
- Best practices.
- Real-world applications.

---

# 16. What's Next?

**Lesson 70 – Feature Engineering**

You'll learn how AI engineers create new, more informative features from existing data, often improving model performance more than changing the algorithm itself.
