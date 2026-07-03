# Chapter 5 – Data Preprocessing

# Lesson 63 – Outliers

> **Outliers are data points that are significantly different from the rest of the dataset. They can reveal valuable insights or introduce serious errors into machine learning models.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what outliers are.
- Learn why outliers occur.
- Identify different types of outliers.
- Detect outliers using statistical and visualization methods.
- Handle outliers appropriately.
- Understand their impact on machine learning algorithms.
- Prepare for interview questions.

---

# Table of Contents

1. What are Outliers?
2. Why Outliers Occur
3. Types of Outliers
4. Why Outliers Matter
5. Detecting Outliers
6. Z-Score Method
7. Interquartile Range (IQR) Method
8. Visualizing Outliers
9. Handling Outliers
10. Real-World AI Applications
11. Best Practices
12. Mini Project
13. Interview Questions
14. Summary
15. What's Next?

---

# 1. What are Outliers?

An **outlier** is a data point that differs significantly from other observations.

Example:

```
Marks

70
72
75
74
73
71
250
```

Here, **250** is an outlier because it is far from the other values.

---

# 2. Why Outliers Occur

Outliers may occur because of:

- Human data entry errors
- Faulty sensors
- Measurement errors
- Rare but valid events
- Fraudulent activities
- Experimental errors

Not every outlier is incorrect. Some represent important real-world events.

---

# 3. Types of Outliers

### Global Outliers

Very different from the entire dataset.

Example:

```
5 7 6 8 9 100
```

---

### Contextual Outliers

Only unusual within a specific context.

Example:

A temperature of **30°C** is normal in summer but unusual in winter.

---

### Collective Outliers

A group of values that appear unusual together.

Example:

Sudden spikes in network traffic indicating a cyberattack.

---

# 4. Why Outliers Matter

```
Raw Data
    │
    ▼
Outliers
    │
    ├── May indicate errors
    └── May indicate rare events
    │
    ▼
Model Performance
```

Outliers can:

- Distort averages
- Reduce prediction accuracy
- Affect regression models
- Increase model bias
- Influence clustering algorithms

---

# 5. Detecting Outliers

Common methods:

- Visualization
- Z-Score
- Interquartile Range (IQR)
- Isolation Forest
- Local Outlier Factor (LOF)

The first two statistical methods are the most common in interviews.

---

# 6. Z-Score Method

The Z-Score measures how many standard deviations a value is from the mean.

Formula:

```
Z = (X - Mean) / Standard Deviation
```

Rule of thumb:

- |Z| > 3 → Potential Outlier

Python Example:

```python
from scipy.stats import zscore

df["Z"] = zscore(df["Marks"])

outliers = df[df["Z"].abs() > 3]
```

---

# 7. Interquartile Range (IQR) Method

The IQR method is robust because it is less affected by extreme values.

Steps:

```
Q1 = 25th Percentile

Q3 = 75th Percentile

IQR = Q3 - Q1
```

Lower Bound:

```
Q1 - 1.5 × IQR
```

Upper Bound:

```
Q3 + 1.5 × IQR
```

Python Example:

```python
Q1 = df["Marks"].quantile(0.25)
Q3 = df["Marks"].quantile(0.75)

IQR = Q3 - Q1

lower = Q1 - 1.5 * IQR
upper = Q3 + 1.5 * IQR

outliers = df[(df["Marks"] < lower) | (df["Marks"] > upper)]
```

---

# 8. Visualizing Outliers

### Box Plot

```
|----[====]----|
       *
```

The isolated point represents an outlier.

Python:

```python
import seaborn as sns

sns.boxplot(x=df["Marks"])
```

---

### Scatter Plot

```python
import matplotlib.pyplot as plt

plt.scatter(df.index, df["Marks"])
plt.show()
```

Outliers appear as isolated points.

---

# 9. Handling Outliers

Common approaches:

### Remove

Useful when values are clearly incorrect.

```python
df = df[(df["Marks"] >= lower) & (df["Marks"] <= upper)]
```

---

### Cap (Winsorization)

Replace extreme values with upper or lower limits.

---

### Transform

Use logarithmic transformations to reduce skewness.

---

### Keep

If the outlier represents a genuine rare event, retain it.

Example:

Fraud detection systems rely on unusual transactions.

---

# 10. Real-World AI Applications

Healthcare

```
Patient Heart Rate
        │
Detect Outliers
        │
Possible Medical Emergency
```

Finance

```
Transactions
      │
Large Unexpected Amount
      │
Fraud Detection
```

Manufacturing

```
Sensor Data
      │
Abnormal Reading
      │
Equipment Failure Prediction
```

---

# 11. Best Practices

- Investigate before removing outliers.
- Understand business context.
- Use visualization before statistical methods.
- Choose detection techniques appropriate for the dataset.
- Document all preprocessing decisions.

---

# 12. Mini Project

Using a dataset:

1. Detect outliers using the IQR method.
2. Detect outliers using Z-Score.
3. Create a box plot.
4. Compare results.
5. Remove or cap outliers.
6. Save the cleaned dataset.

---

# 13. Interview Questions

### What is an outlier?

A data point significantly different from the rest of the observations.

### Why are outliers important?

They may represent errors or valuable rare events.

### Which methods detect outliers?

- Z-Score
- IQR
- Box Plot
- Isolation Forest
- LOF

### Which method is more robust?

The IQR method because it is less affected by extreme values.

### Should all outliers be removed?

No. Some represent important real-world information.

---

# 14. Summary

You learned:

- What outliers are.
- Why they occur.
- Types of outliers.
- Z-Score method.
- IQR method.
- Visualization techniques.
- Handling strategies.
- Real-world applications.

---

# 15. What's Next?

**Lesson 64 – Data Encoding**

You'll learn why machine learning models cannot understand categorical text directly and how encoding converts human-readable categories into numerical values suitable for AI algorithms.
