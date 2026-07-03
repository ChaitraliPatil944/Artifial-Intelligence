# Chapter 5 – Data Preprocessing

# Lesson 68 – Standardization

> **Standardization transforms numerical features so they have a mean of 0 and a standard deviation of 1. It is one of the most widely used preprocessing techniques in Machine Learning.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Standardization is.
- Learn why it is needed.
- Understand the mathematics behind Z-score normalization.
- Apply StandardScaler using Scikit-Learn.
- Know when Standardization should and should not be used.
- Prepare for interview questions.

---

# Table of Contents

1. What is Standardization?
2. Why Standardization is Needed
3. Mathematical Formula
4. Mean and Standard Deviation Refresher
5. How Standardization Works
6. StandardScaler
7. Before vs After Standardization
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

# 1. What is Standardization?

Standardization is a feature scaling technique that transforms data so that:

- Mean = 0
- Standard Deviation = 1

Instead of changing the shape of the distribution, it changes the scale.

---

# 2. Why Standardization is Needed

Consider two features:

| Feature | Range |
|---------|------:|
| Age | 18–60 |
| Salary | 25,000–2,000,000 |

Without scaling, salary dominates learning.

Standardization makes both features comparable.

---

# 3. Mathematical Formula

The Z-score formula is:

```
Z = (X - μ) / σ
```

Where:

- X = Original Value
- μ = Mean
- σ = Standard Deviation

If a value equals the mean:

```
Z = 0
```

---

# 4. Mean and Standard Deviation Refresher

Mean:

```
Sum of values
--------------
Number of values
```

Standard Deviation measures how spread out the values are.

```
Small SD
●●●●●

Large SD
●     ●   ●      ●
```

---

# 5. How Standardization Works

Original Values

```
10
20
30
40
50
```

↓

Calculate Mean

↓

Calculate Standard Deviation

↓

Apply Z-score

↓

Standardized Values

```
-1.41
-0.71
0.00
0.71
1.41
```

---

# 6. StandardScaler

Scikit-Learn implementation:

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

X_train_scaled = scaler.fit_transform(X_train)

X_test_scaled = scaler.transform(X_test)
```

Always use:

- `fit()` only on training data.
- `transform()` on testing data.

---

# 7. Before vs After Standardization

Before

```
Age      Salary

20       30000

45       900000

60       1500000
```

After

```
Age      Salary

-1.12    -0.95

0.45      0.38

1.21      1.42
```

Different units become comparable.

---

# 8. Algorithms That Benefit

Standardization is recommended for:

- Logistic Regression
- Linear Regression
- Support Vector Machines
- Neural Networks
- K-Nearest Neighbors
- PCA
- K-Means

Tree-based models generally do not require it.

---

# 9. Advantages

- Faster optimization.
- Better gradient descent convergence.
- Prevents large-valued features from dominating.
- Improves numerical stability.
- Widely supported.

---

# 10. Limitations

- Sensitive to outliers.
- Does not bound values between fixed limits.
- Less suitable when extreme values dominate the dataset.

For datasets with many outliers, RobustScaler may be preferable.

---

# 11. Best Practices

- Split train and test data first.
- Fit the scaler only on training data.
- Save the fitted scaler for deployment.
- Apply the same scaler during inference.

Workflow

```
Train Data
     │
fit()
     │
transform()
     │
Train Model

Test Data
     │
transform()
     │
Evaluate
```

---

# 12. Real-World Applications

Examples:

- Credit Risk Prediction
- House Price Prediction
- Face Recognition
- Medical Diagnosis
- Customer Churn Prediction

Standardization is commonly used before training deep learning and classical ML models.

---

# 13. Mini Project

Using a housing dataset:

1. Load numerical features.
2. Split data into train and test sets.
3. Apply `StandardScaler`.
4. Compare means before and after scaling.
5. Train a Logistic Regression or Linear Regression model.

---

# 14. Interview Questions

### What is Standardization?

A feature scaling technique that converts features to zero mean and unit variance.

### What is the formula?

```
Z = (X - μ) / σ
```

### Why fit only on training data?

To prevent data leakage.

### Which Scikit-Learn class performs Standardization?

```python
from sklearn.preprocessing import StandardScaler
```

### Does Standardization remove outliers?

No. It scales values but does not eliminate outliers.

---

# 15. Summary

You learned:

- What Standardization is.
- Why it is important.
- Z-score transformation.
- StandardScaler.
- Best practices.
- Advantages and limitations.
- Real-world applications.

---

# 16. What's Next?

**Lesson 69 – Normalization**

You'll learn Min-Max Scaling, normalization techniques, how they differ from Standardization, and when each should be preferred in real-world machine learning projects.
