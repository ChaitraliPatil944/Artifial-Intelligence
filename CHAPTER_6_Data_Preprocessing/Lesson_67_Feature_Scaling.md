# Chapter 5 – Data Preprocessing

# Lesson 67 – Feature Scaling

> **Machine Learning algorithms compare numbers. If one feature has values in millions while another ranges from 0 to 1, the larger feature can dominate learning. Feature Scaling puts features on a comparable scale.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what feature scaling is.
- Learn why feature scaling is required.
- Identify algorithms that require scaling.
- Compare different scaling techniques.
- Apply feature scaling using Scikit-Learn.
- Prepare for interview questions.

---

# Table of Contents

1. What is Feature Scaling?
2. Why Feature Scaling is Needed
3. When Feature Scaling is Required
4. Algorithms That Need Scaling
5. Algorithms That Don't Usually Need Scaling
6. Types of Feature Scaling
7. Feature Scaling Workflow
8. Scikit-Learn Implementation
9. Common Mistakes
10. Real-World Applications
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

---

# 1. What is Feature Scaling?

Feature Scaling is the process of transforming numerical features so they have comparable ranges.

Example:

| Age | Salary |
|----:|-------:|
| 25 | 35000 |
| 40 | 90000 |

Salary values are much larger than age values.

---

# 2. Why Feature Scaling is Needed

Imagine measuring distance.

```
Feature A

0 - 10

Feature B

0 - 1,000,000
```

Most distance-based algorithms will focus almost entirely on **Feature B**.

Scaling balances the influence of each feature.

---

# 3. When Feature Scaling is Required

Scaling is recommended when:

- Features have very different units.
- Distance calculations are important.
- Gradient-based optimization is used.

Examples:

- Height (cm)
- Weight (kg)
- Salary (₹)
- Age (years)

---

# 4. Algorithms That Need Scaling

Feature scaling is important for:

- K-Nearest Neighbors (KNN)
- Support Vector Machines (SVM)
- K-Means Clustering
- Logistic Regression
- Linear Regression (often beneficial)
- Neural Networks
- PCA

These algorithms rely on distances or optimization.

---

# 5. Algorithms That Don't Usually Need Scaling

Tree-based models are generally unaffected:

- Decision Trees
- Random Forest
- XGBoost
- LightGBM
- CatBoost

These split data based on thresholds rather than distances.

---

# 6. Types of Feature Scaling

Common techniques:

- Standardization
- Normalization
- Robust Scaling
- Min-Max Scaling
- Max Absolute Scaling

In this course:

- Lesson 68 → Standardization
- Lesson 69 → Normalization

---

# 7. Feature Scaling Workflow

```
Raw Data
    │
    ▼
Split Train/Test
    │
    ▼
Fit Scaler on Training Data
    │
    ▼
Transform Training Data
    │
    ▼
Transform Test Data
    │
    ▼
Train Model
```

**Important:** Never fit the scaler on the test dataset.

---

# 8. Scikit-Learn Implementation

Standard Scaler:

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

Min-Max Scaler:

```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()

X_scaled = scaler.fit_transform(X)
```

---

# 9. Common Mistakes

- Scaling before train-test split.
- Fitting the scaler on the entire dataset.
- Scaling target labels unnecessarily.
- Applying different scalers to training and testing data.

These mistakes can introduce **data leakage**.

---

# 10. Real-World Applications

Example:

```
Customer Data

Age
Income
Loan Amount

        │

Feature Scaling

        │

Machine Learning Model

        │

Loan Approval Prediction
```

Feature scaling is common in finance, healthcare, computer vision, and recommendation systems.

---

# 11. Mini Project

Using a housing dataset:

1. Identify numerical features.
2. Split the dataset into training and testing sets.
3. Apply StandardScaler.
4. Compare values before and after scaling.
5. Train a simple ML model and compare performance.

---

# 12. Interview Questions

### What is feature scaling?

A preprocessing technique that transforms numerical features to comparable ranges.

### Why is feature scaling important?

It prevents large-valued features from dominating model learning.

### Which algorithms require feature scaling?

KNN, SVM, K-Means, PCA, Logistic Regression, and Neural Networks.

### Do Decision Trees require feature scaling?

Generally, no.

### Why should scaling happen after train-test split?

To prevent data leakage.

---

# 13. Summary

You learned:

- What feature scaling is.
- Why it is important.
- Which algorithms need scaling.
- Common scaling techniques.
- Correct preprocessing workflow.
- Scikit-Learn implementation.
- Common mistakes.

---

# 14. What's Next?

**Lesson 68 – Standardization**

You'll learn the mathematics behind Standardization, the Z-score transformation, why it creates zero-mean and unit-variance features, and when it is preferred over Normalization.
