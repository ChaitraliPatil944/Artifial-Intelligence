# Chapter 5 – Data Preprocessing

# Lesson 72 – Data Leakage

> **Data Leakage is one of the most dangerous mistakes in Machine Learning. A model that accidentally learns information it should never have access to may achieve excellent test scores but fail completely in the real world.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Data Leakage is.
- Learn why it is dangerous.
- Identify different types of leakage.
- Prevent leakage in ML pipelines.
- Use Scikit-Learn correctly to avoid leakage.
- Prepare for interview questions.

---

# Table of Contents

1. What is Data Leakage?
2. Why Data Leakage is Dangerous
3. Types of Data Leakage
4. Common Causes
5. Real-World Examples
6. Preventing Data Leakage
7. Scikit-Learn Pipelines
8. Best Practices
9. Mini Project
10. Interview Questions
11. Summary
12. What's Next?

---

# 1. What is Data Leakage?

Data Leakage occurs when information that would not be available during real-world prediction accidentally becomes available during model training.

```
Future Information
        │
        ▼
Training Data
        │
        ▼
Artificially High Accuracy
```

The model appears excellent but has learned from information it should never see.

---

# 2. Why Data Leakage is Dangerous

Imagine predicting tomorrow's stock price after secretly reading tomorrow's newspaper.

Your prediction looks perfect.

In reality, the model cheats.

Machine Learning models behave similarly when leakage occurs.

Consequences:

- Unrealistic accuracy
- Poor production performance
- Wrong business decisions
- Loss of trust

---

# 3. Types of Data Leakage

## Target Leakage

Features directly reveal the target.

Example:

Predicting loan default while including a column:

```
Loan Status = Defaulted
```

The answer is already present.

---

## Train-Test Contamination

Information from the test set leaks into training.

Example:

```
Entire Dataset
      │
Scale Everything
      │
Split Data
```

Correct workflow:

```
Split Data
      │
Fit Scaler on Train
      │
Transform Train
      │
Transform Test
```

---

## Time Leakage

Future information is used to predict the past.

Example:

Predicting January sales using February data.

---

# 4. Common Causes

- Scaling before train-test split
- Feature selection using the full dataset
- Filling missing values using all data
- Duplicate records across train and test sets
- Using future information
- Manual preprocessing mistakes

---

# 5. Real-World Examples

Healthcare

```
Predict Disease

↓

Include Future Diagnosis

↓

100% Accuracy

↓

Worthless Model
```

Finance

```
Predict Fraud

↓

Use Fraud Investigation Result

↓

Leakage
```

Recommendation Systems

```
Predict Purchase

↓

Include Future Purchases

↓

Invalid Evaluation
```

---

# 6. Preventing Data Leakage

Always follow this workflow:

```
Raw Data
    │
    ▼
Train-Test Split
    │
    ▼
Fit Preprocessing on Train
    │
    ▼
Transform Train
    │
    ▼
Transform Test
    │
    ▼
Train Model
```

Golden Rule:

**The test dataset must remain completely unseen until evaluation.**

---

# 7. Scikit-Learn Pipelines

Pipelines reduce leakage by combining preprocessing and modeling.

```python
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression

pipeline = Pipeline([
    ("scaler", StandardScaler()),
    ("model", LogisticRegression())
])

pipeline.fit(X_train, y_train)
```

Benefits:

- Cleaner workflow
- Less human error
- Reduced leakage risk
- Easier deployment

---

# 8. Best Practices

- Split data before preprocessing.
- Never fit preprocessing on test data.
- Keep future information out of training.
- Use pipelines.
- Validate every preprocessing step.
- Maintain reproducible workflows.

---

# 9. Mini Project

Using any dataset:

1. Split into train and test sets.
2. Apply StandardScaler correctly.
3. Train a Logistic Regression model.
4. Repeat by scaling before splitting.
5. Compare the evaluation results and explain why they differ.

---

# 10. Interview Questions

### What is Data Leakage?

The accidental use of information during training that would not be available during real-world prediction.

### Why is Data Leakage dangerous?

It produces misleadingly high evaluation scores and poor real-world performance.

### Name two common types of Data Leakage.

- Target Leakage
- Train-Test Contamination

### How can Pipelines help?

They ensure preprocessing is fitted only on training data.

### What is the golden rule?

Keep the test dataset completely unseen until final evaluation.

---

# 11. Summary

You learned:

- What Data Leakage is.
- Why it is dangerous.
- Types of leakage.
- Common causes.
- Prevention strategies.
- Scikit-Learn Pipelines.
- Best practices.

---

# 12. What's Next?

**Lesson 73 – Class Imbalance**

You'll learn why some datasets contain far more examples of one class than another, how this affects model performance, and techniques such as oversampling, undersampling, and SMOTE to handle imbalanced data.
