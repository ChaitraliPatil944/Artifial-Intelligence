# Chapter 5 – Data Preprocessing

# Lesson 71 – Feature Selection

> **Not every feature helps a Machine Learning model. Feature Selection identifies the most useful features while removing irrelevant, redundant, or noisy ones, leading to faster, simpler, and often more accurate models.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Feature Selection is.
- Learn why Feature Selection is important.
- Differentiate Feature Selection from Feature Engineering.
- Explore Filter, Wrapper, and Embedded methods.
- Implement Feature Selection using Scikit-Learn.
- Prepare for interview questions.

---

# Table of Contents

1. What is Feature Selection?
2. Why Feature Selection is Needed
3. Feature Selection Workflow
4. Feature Selection vs Feature Engineering
5. Types of Feature Selection
6. Filter Methods
7. Wrapper Methods
8. Embedded Methods
9. Feature Importance
10. Python Implementation
11. Best Practices
12. Real-World Applications
13. Mini Project
14. Interview Questions
15. Summary
16. What's Next?

---

# 1. What is Feature Selection?

Feature Selection is the process of choosing the most relevant features for training a Machine Learning model.

Instead of using every available feature, we keep only those that contribute meaningful information.

```
100 Features
      │
      ▼
Feature Selection
      │
      ▼
25 Useful Features
      │
      ▼
Machine Learning Model
```

---

# 2. Why Feature Selection is Needed

Too many features can create problems:

- Overfitting
- Increased training time
- Higher memory usage
- Reduced interpretability
- Noisy predictions

Removing unnecessary features often improves performance.

---

# 3. Feature Selection Workflow

```
Collect Data
      │
      ▼
Clean Data
      │
      ▼
Engineer Features
      │
      ▼
Select Important Features
      │
      ▼
Train Model
      │
      ▼
Evaluate
```

---

# 4. Feature Selection vs Feature Engineering

| Feature Engineering | Feature Selection |
|---------------------|------------------|
| Creates new features | Chooses existing features |
| Adds information | Removes unnecessary information |
| Uses domain knowledge | Uses statistical or model-based methods |

Both are complementary.

---

# 5. Types of Feature Selection

There are three major approaches:

### Filter Methods

Evaluate features using statistical tests before model training.

### Wrapper Methods

Train multiple models using different feature subsets.

### Embedded Methods

Feature selection happens automatically during model training.

---

# 6. Filter Methods

Common techniques:

- Correlation
- Chi-Square Test
- ANOVA F-Test
- Mutual Information

Example using correlation:

```
Feature A  ---- 0.95 ---- Target

Feature B  ---- 0.05 ---- Target
```

Feature A is likely more useful.

Python:

```python
from sklearn.feature_selection import SelectKBest
from sklearn.feature_selection import chi2

selector = SelectKBest(score_func=chi2, k=5)
```

---

# 7. Wrapper Methods

Wrapper methods evaluate different combinations of features.

Popular technique:

### Recursive Feature Elimination (RFE)

```
All Features
      │
      ▼
Train Model
      │
      ▼
Remove Least Important Feature
      │
      ▼
Repeat
```

Python:

```python
from sklearn.feature_selection import RFE
from sklearn.linear_model import LogisticRegression

model = LogisticRegression()

selector = RFE(model, n_features_to_select=5)

selector.fit(X, y)
```

Wrapper methods are accurate but computationally expensive.

---

# 8. Embedded Methods

Feature selection occurs while the model learns.

Examples:

- Lasso Regression
- Decision Trees
- Random Forest
- XGBoost

Example:

```python
from sklearn.linear_model import Lasso
```

Tree-based models provide feature importance scores automatically.

---

# 9. Feature Importance

Many models estimate how important each feature is.

Example:

```
Income      0.52

Age         0.31

Gender      0.11

Zip Code    0.06
```

Higher scores indicate greater influence.

---

# 10. Python Implementation

Using SelectKBest:

```python
from sklearn.feature_selection import SelectKBest, f_classif

selector = SelectKBest(score_func=f_classif, k=5)

X_new = selector.fit_transform(X, y)
```

Using Random Forest:

```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier()

model.fit(X, y)

print(model.feature_importances_)
```

---

# 11. Best Practices

- Remove highly correlated features.
- Avoid selecting features using the test set.
- Combine domain knowledge with statistical methods.
- Validate model performance after selection.
- Keep preprocessing reproducible.

---

# 12. Real-World Applications

Healthcare

```
Hundreds of Medical Tests
          │
Feature Selection
          │
Most Informative Tests
          │
Disease Prediction
```

Finance

```
Customer Data
      │
Feature Selection
      │
Loan Risk Model
```

Computer Vision

```
Extracted Features
       │
Feature Selection
       │
Image Classifier
```

---

# 13. Mini Project

Using a dataset:

1. Train a baseline model.
2. Apply SelectKBest.
3. Apply RFE.
4. Compare model accuracy.
5. List the selected features.

---

# 14. Interview Questions

### What is Feature Selection?

The process of selecting the most relevant input features for model training.

### Why is Feature Selection important?

It reduces overfitting, improves speed, and simplifies models.

### Name the three major Feature Selection methods.

- Filter
- Wrapper
- Embedded

### What is RFE?

Recursive Feature Elimination removes the least important feature iteratively until the desired number of features remains.

### Which tree-based models provide feature importance?

- Decision Trees
- Random Forest
- XGBoost

---

# 15. Summary

You learned:

- What Feature Selection is.
- Why it matters.
- Filter, Wrapper, and Embedded methods.
- RFE and SelectKBest.
- Feature Importance.
- Python implementations.
- Real-world applications.

---

# 16. What's Next?

**Lesson 72 – Data Leakage**

You'll learn one of the most dangerous mistakes in Machine Learning: how information from the future or the test dataset can accidentally leak into training, producing unrealistically high accuracy and unreliable models.
