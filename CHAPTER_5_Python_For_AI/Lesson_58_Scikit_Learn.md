# Chapter 4 – Python for AI

# Lesson 58 – Scikit-Learn

> **Scikit-Learn is the toolbox that turns data into intelligent machine learning models with just a few lines of Python code.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Scikit-Learn is.
- Learn why it was created.
- Explore its architecture and workflow.
- Build your first machine learning model.
- Learn about preprocessing, training, testing, and evaluation.
- Prepare for common interview questions.

---

# Table of Contents

1. What is Scikit-Learn?
2. Why Scikit-Learn was Created
3. Features of Scikit-Learn
4. Installation
5. Machine Learning Workflow
6. Loading Datasets
7. Train-Test Split
8. Building Your First Model
9. Model Evaluation
10. Pipelines
11. Common Algorithms
12. Real-World Applications
13. Mini Project
14. Interview Questions
15. Summary
16. What's Next?

---

# 1. What is Scikit-Learn?

Scikit-Learn (sklearn) is one of the most popular Python libraries for Machine Learning.

It provides simple and efficient tools for:

- Classification
- Regression
- Clustering
- Model Evaluation
- Feature Selection
- Data Preprocessing

Import:

```python
import sklearn
```

---

# 2. Why Scikit-Learn was Created

Machine learning algorithms are mathematically complex.

Instead of implementing them from scratch every time, Scikit-Learn provides optimized implementations through a consistent API.

---

# 3. Features of Scikit-Learn

- Easy to learn
- Consistent API
- Excellent documentation
- Built on NumPy, SciPy and Matplotlib
- Supports supervised and unsupervised learning
- Large community support

---

# 4. Installation

```bash
pip install scikit-learn
```

Import commonly used modules:

```python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
```

---

# 5. Machine Learning Workflow

```
Collect Data
      │
      ▼
Clean Data
      │
      ▼
Split Dataset
      │
      ▼
Train Model
      │
      ▼
Predict
      │
      ▼
Evaluate
```

Scikit-Learn simplifies each of these stages.

---

# 6. Loading Datasets

Built-in datasets:

```python
from sklearn.datasets import load_iris

iris = load_iris()
```

Popular datasets:

- Iris
- Wine
- Breast Cancer
- Digits

---

# 7. Train-Test Split

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

Purpose:

- Training data teaches the model.
- Testing data measures performance on unseen examples.

---

# 8. Building Your First Model

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(X_train, y_train)

predictions = model.predict(X_test)
```

Important methods:

- fit()
- predict()
- score()

---

# 9. Model Evaluation

Classification metrics:

- Accuracy
- Precision
- Recall
- F1 Score

Regression metrics:

- MAE
- MSE
- RMSE
- R² Score

Example:

```python
from sklearn.metrics import accuracy_score

accuracy = accuracy_score(y_test, predictions)
```

---

# 10. Pipelines

Pipelines automate preprocessing and training.

```python
from sklearn.pipeline import Pipeline
```

Workflow:

```
Raw Data
    │
    ▼
Preprocessing
    │
    ▼
Model
    │
    ▼
Prediction
```

Advantages:

- Cleaner code
- Fewer mistakes
- Easier deployment

---

# 11. Common Algorithms

Scikit-Learn supports:

- Linear Regression
- Logistic Regression
- K-Nearest Neighbors
- Decision Trees
- Random Forest
- Support Vector Machine
- Naive Bayes
- K-Means
- PCA

You will study each of these in later chapters.

---

# 12. Real-World Applications

Scikit-Learn is widely used for:

- Customer churn prediction
- Fraud detection
- Email spam filtering
- House price prediction
- Disease diagnosis
- Recommendation systems
- Sales forecasting

---

# 13. Mini Project

Build an Iris Flower Classifier.

Steps:

1. Load the Iris dataset.
2. Split into training and testing sets.
3. Train a Decision Tree classifier.
4. Predict flower species.
5. Measure model accuracy.

---

# 14. Interview Questions

### What is Scikit-Learn?

A Python library providing efficient implementations of machine learning algorithms.

### Why is train_test_split important?

It evaluates how well a model performs on unseen data.

### Difference between fit() and predict()?

- fit() trains the model.
- predict() generates predictions using the trained model.

### What is a pipeline?

A sequence of preprocessing and model-building steps executed automatically.

---

# 15. Summary

You learned:

- What Scikit-Learn is.
- Why it was created.
- Loading datasets.
- Train-test splitting.
- Model training.
- Prediction.
- Evaluation.
- Pipelines.
- Common ML algorithms.

---

# 16. What's Next?

🎉 Congratulations!

You have completed **Chapter 4 – Python for AI**.

In **Chapter 5 – Data Preprocessing**, you'll learn how real-world data is collected, cleaned, transformed, encoded, scaled, and prepared before it can be used to train machine learning models.

The first lesson is:

**Lesson 59 – Data Collection**
