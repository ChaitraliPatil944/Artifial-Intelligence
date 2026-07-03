# Chapter 5 – Data Preprocessing

# Lesson 73 – Class Imbalance

> **Real-world datasets are rarely perfectly balanced. When one class heavily outnumbers another, Machine Learning models can become biased toward the majority class. Handling class imbalance is essential for building reliable AI systems.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what class imbalance is.
- Learn why it occurs.
- Understand its effect on Machine Learning models.
- Explore techniques to handle imbalanced datasets.
- Learn about SMOTE and class weighting.
- Prepare for interview questions.

---

# Table of Contents

1. What is Class Imbalance?
2. Why Class Imbalance Occurs
3. Why Accuracy Can Be Misleading
4. Detecting Class Imbalance
5. Oversampling
6. Undersampling
7. SMOTE
8. Class Weights
9. Choosing the Right Technique
10. Best Practices
11. Real-World Applications
12. Mini Project
13. Interview Questions
14. Summary
15. What's Next?

---

# 1. What is Class Imbalance?

A dataset is **imbalanced** when one class contains far more samples than another.

Example:

```
Loan Approved

Yes : 950

No  : 50
```

The model sees many more "Yes" examples than "No".

---

# 2. Why Class Imbalance Occurs

Imbalanced datasets are common because rare events are, well... rare.

Examples:

- Fraud transactions
- Credit card defaults
- Cancer diagnosis
- Manufacturing defects
- Network intrusions
- Equipment failures

---

# 3. Why Accuracy Can Be Misleading

Dataset:

```
990 Legitimate

10 Fraud
```

Model prediction:

```
Predict Everything as Legitimate
```

Results:

```
Accuracy = 99%
```

But:

```
Fraud Detection = 0%
```

The model completely fails at detecting fraud despite excellent accuracy.

---

# 4. Detecting Class Imbalance

Using Pandas:

```python
df["Target"].value_counts()
```

Percentage:

```python
df["Target"].value_counts(normalize=True) * 100
```

Visualization:

```python
import seaborn as sns

sns.countplot(x="Target", data=df)
```

---

# 5. Oversampling

Oversampling increases the number of minority samples.

```
Before

Majority: ██████████

Minority: ██

↓

After

Majority: ██████████

Minority: ██████████
```

Advantages:

- Retains majority data
- Helps minority learning

Disadvantage:

- May increase overfitting

---

# 6. Undersampling

Undersampling reduces the majority class.

```
Before

██████████

██

↓

After

████

████
```

Advantages:

- Faster training
- Smaller datasets

Disadvantages:

- Loss of useful information

---

# 7. SMOTE

SMOTE stands for:

**Synthetic Minority Oversampling Technique**

Instead of copying minority samples, SMOTE creates **new synthetic samples**.

```
Minority Samples

●      ●

      ●

↓

Generate New Samples

●  ●  ●
```

Python:

```python
from imblearn.over_sampling import SMOTE

smote = SMOTE(random_state=42)

X_resampled, y_resampled = smote.fit_resample(X, y)
```

SMOTE is one of the most popular interview topics.

---

# 8. Class Weights

Some algorithms allow assigning greater importance to minority classes.

Example:

```python
from sklearn.linear_model import LogisticRegression

model = LogisticRegression(class_weight="balanced")
```

Useful when oversampling is not desirable.

---

# 9. Choosing the Right Technique

| Situation | Recommended Technique |
|-----------|-----------------------|
| Small minority class | SMOTE |
| Huge majority class | Undersampling |
| Limited memory | Undersampling |
| Preserve all data | Oversampling |
| Tree models | Class Weights or Balanced Sampling |

---

# 10. Best Practices

- Don't rely only on accuracy.
- Use Precision, Recall, and F1-score.
- Apply resampling **only to the training set**.
- Validate with cross-validation.
- Compare multiple balancing techniques.

---

# 11. Real-World Applications

Fraud Detection

```
Transactions
      │
Class Imbalance
      │
SMOTE
      │
Fraud Classifier
```

Healthcare

```
Patient Records
      │
Rare Disease Cases
      │
Balanced Dataset
      │
Disease Prediction
```

Cybersecurity

```
Network Logs
      │
Rare Attacks
      │
Intrusion Detection
```

---

# 12. Mini Project

Using an imbalanced dataset:

1. Check class distribution.
2. Train a baseline classifier.
3. Apply SMOTE.
4. Retrain the model.
5. Compare Accuracy, Precision, Recall, and F1-score.

---

# 13. Interview Questions

### What is class imbalance?

A situation where one class has significantly more samples than another.

### Why is accuracy misleading?

A model may predict only the majority class and still achieve high accuracy.

### What is SMOTE?

Synthetic Minority Oversampling Technique that generates synthetic minority samples.

### Difference between Oversampling and Undersampling?

- Oversampling increases minority samples.
- Undersampling reduces majority samples.

### Should SMOTE be applied before train-test split?

No. Apply SMOTE **only to the training data** to avoid data leakage.

---

# 14. Summary

You learned:

- What class imbalance is.
- Why it occurs.
- Why accuracy alone is insufficient.
- Oversampling.
- Undersampling.
- SMOTE.
- Class weights.
- Best practices.

---

# 15. What's Next?

**Lesson 74 – Data Augmentation**

You'll learn how AI engineers artificially increase dataset size using transformations for images, text, and audio, improving model robustness without collecting new data.
