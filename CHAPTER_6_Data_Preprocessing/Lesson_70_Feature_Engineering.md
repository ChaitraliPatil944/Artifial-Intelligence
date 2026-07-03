# Chapter 5 – Data Preprocessing

# Lesson 70 – Feature Engineering

> **Feature Engineering is the process of creating better input features from raw data so that machine learning models can learn more effectively. In many real-world projects, better features improve performance more than changing the algorithm itself.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Feature Engineering is.
- Learn why it is one of the most important skills in AI.
- Differentiate Feature Engineering, Feature Extraction, and Feature Selection.
- Learn common Feature Engineering techniques.
- Create new features using Python.
- Prepare for interview questions.

---

# Table of Contents

1. What is Feature Engineering?
2. Why Feature Engineering is Important
3. History and Motivation
4. Feature Engineering Workflow
5. Types of Feature Engineering
6. Common Techniques
7. Python Examples
8. Feature Engineering vs Feature Selection
9. Best Practices
10. Real-World Applications
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

---

# 1. What is Feature Engineering?

Feature Engineering is the process of transforming raw data into meaningful features that help machine learning algorithms make better predictions.

Instead of feeding raw data directly into a model, we create informative variables.

Example:

```
Date of Birth
        │
        ▼
Age
```

Age is usually more useful than the raw birth date.

---

# 2. Why Feature Engineering is Important

Good features help models discover useful patterns.

```
Raw Data
    │
    ▼
Feature Engineering
    │
    ▼
Better Features
    │
    ▼
Better Predictions
```

A simple model with excellent features often outperforms a complex model trained on poor features.

---

# 3. History and Motivation

Before Deep Learning became popular, Feature Engineering was the most important part of Machine Learning.

Data scientists manually designed features using domain knowledge.

Even today, Feature Engineering remains essential for:

- Structured data
- Business analytics
- Finance
- Healthcare
- Fraud detection

---

# 4. Feature Engineering Workflow

```
Collect Data
      │
      ▼
Clean Data
      │
      ▼
Understand Business Problem
      │
      ▼
Create New Features
      │
      ▼
Train Model
      │
      ▼
Evaluate Performance
```

---

# 5. Types of Feature Engineering

### Numerical Features

Examples:

- BMI = Weight / Height²
- Price per Unit

### Date & Time Features

Extract:

- Year
- Month
- Day
- Weekday
- Hour

### Text Features

- Word Count
- Character Count
- Sentiment Score

### Image Features

- Edges
- Corners
- Color Histograms

### Aggregated Features

Examples:

- Total Purchase Amount
- Average Monthly Spending

---

# 6. Common Techniques

### Creating New Features

```python
df["BMI"] = df["Weight"] / (df["Height"] ** 2)
```

### Combining Features

```python
df["Full_Name"] = df["First"] + " " + df["Last"]
```

### Extracting Date Features

```python
df["Date"] = pd.to_datetime(df["Date"])

df["Month"] = df["Date"].dt.month

df["Year"] = df["Date"].dt.year
```

### Polynomial Features

```python
from sklearn.preprocessing import PolynomialFeatures

poly = PolynomialFeatures(degree=2)
```

Useful when relationships are non-linear.

---

# 7. Python Examples

Create Age Group:

```python
df["Age_Group"] = pd.cut(
    df["Age"],
    bins=[0,18,35,60,100],
    labels=["Child","Young","Adult","Senior"]
)
```

Extract Email Domain:

```python
df["Domain"] = df["Email"].str.split("@").str[1]
```

---

# 8. Feature Engineering vs Feature Selection

| Feature Engineering | Feature Selection |
|---------------------|------------------|
| Creates new features | Chooses existing features |
| Adds information | Removes unnecessary information |
| Uses domain knowledge | Uses statistical methods |

Example:

```
Salary
Experience

↓

Salary / Experience

(New Feature)
```

---

# 9. Best Practices

- Understand the business problem.
- Create meaningful features.
- Avoid creating redundant features.
- Prevent data leakage.
- Validate whether new features improve model performance.

---

# 10. Real-World Applications

Healthcare

```
Height + Weight
        │
        ▼
BMI
        │
Disease Prediction
```

Finance

```
Income + Loan
        │
Debt-to-Income Ratio
        │
Loan Approval
```

E-commerce

```
Purchase History
        │
Average Order Value
        │
Customer Segmentation
```

---

# 11. Mini Project

Using a customer dataset:

1. Create Age Groups.
2. Extract Month from registration date.
3. Create Total Purchase feature.
4. Create Average Purchase feature.
5. Compare model accuracy before and after Feature Engineering.

---

# 12. Interview Questions

### What is Feature Engineering?

The process of creating new, meaningful features from raw data to improve machine learning models.

### Why is Feature Engineering important?

Better features often improve model performance more than changing algorithms.

### Difference between Feature Engineering and Feature Selection?

Feature Engineering creates new features, while Feature Selection chooses the most useful existing features.

### Give examples of engineered features.

- BMI
- Age
- Debt-to-Income Ratio
- Purchase Frequency

---

# 13. Summary

You learned:

- What Feature Engineering is.
- Why it is important.
- Types of engineered features.
- Python examples.
- Feature Engineering vs Feature Selection.
- Real-world applications.
- Best practices.

---

# 14. What's Next?

**Lesson 71 – Feature Selection**

You'll learn how to identify the most useful features, remove irrelevant variables, reduce overfitting, improve training speed, and build simpler, more accurate machine learning models.
