# Chapter 4 – Python for AI

# Lesson 54 – Matplotlib

> **Matplotlib transforms numbers into pictures, making patterns visible that would otherwise remain hidden.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Matplotlib is.
- Learn why data visualization is important.
- Create common charts using Matplotlib.
- Customize graphs with titles, labels, legends, and grids.
- Understand where Matplotlib fits in the AI workflow.
- Prepare for interview questions related to visualization.

---

# Table of Contents

1. What is Matplotlib?
2. Why Matplotlib was Created
3. Installing Matplotlib
4. Your First Plot
5. Line Charts
6. Bar Charts
7. Scatter Plots
8. Histograms
9. Pie Charts
10. Customizing Charts
11. Multiple Plots
12. Saving Figures
13. Real-World AI Applications
14. Mini Project
15. Interview Questions
16. Summary
17. What's Next?

---

# 1. What is Matplotlib?

Matplotlib is a Python library used to create graphs and charts.

```python
import matplotlib.pyplot as plt
```

It helps convert raw numerical data into visual insights.

---

# 2. Why Matplotlib was Created

Looking at thousands of numbers is difficult.

Graphs help us quickly identify:

- Trends
- Patterns
- Outliers
- Relationships

AI engineers visualize data before training models.

---

# 3. Installing Matplotlib

```bash
pip install matplotlib
```

Import:

```python
import matplotlib.pyplot as plt
```

---

# 4. Your First Plot

```python
import matplotlib.pyplot as plt

x = [1,2,3,4]
y = [2,4,6,8]

plt.plot(x, y)
plt.show()
```

---

# 5. Line Charts

Best used for continuous data.

```python
plt.plot(x, y)
plt.title("Sales Trend")
plt.xlabel("Month")
plt.ylabel("Sales")
plt.show()
```

ASCII

```
Sales
 ^
 |      *
 |    *
 |  *
 |*
 +--------------> Month
```

---

# 6. Bar Charts

Used to compare categories.

```python
subjects = ["Math","AI","Python"]
marks = [80,95,90]

plt.bar(subjects, marks)
plt.show()
```

---

# 7. Scatter Plots

Shows relationships between variables.

```python
plt.scatter(x, y)
plt.show()
```

Useful for detecting clusters and correlations.

---

# 8. Histograms

Displays the distribution of data.

```python
import numpy as np

data = np.random.randn(1000)

plt.hist(data, bins=20)
plt.show()
```

---

# 9. Pie Charts

Shows proportions.

```python
sizes = [45,30,25]

plt.pie(sizes, labels=["Python","AI","Cloud"], autopct="%1.1f%%")
plt.show()
```

---

# 10. Customizing Charts

```python
plt.plot(x, y)

plt.title("Performance")

plt.xlabel("Epoch")

plt.ylabel("Accuracy")

plt.grid(True)

plt.legend(["Accuracy"])

plt.show()
```

---

# 11. Multiple Plots

```python
plt.subplot(1,2,1)
plt.plot(x,y)

plt.subplot(1,2,2)
plt.bar(x,y)

plt.show()
```

Useful when comparing multiple visualizations.

---

# 12. Saving Figures

```python
plt.savefig("graph.png")
```

Common formats:

- PNG
- JPG
- PDF
- SVG

---

# 13. Real-World AI Applications

Matplotlib is used to visualize:

- Training loss
- Accuracy curves
- Confusion matrices
- Feature importance
- Data distributions
- Prediction results

Typical AI Workflow

```
Collect Data
      │
      ▼
Clean Data
      │
      ▼
Visualize Data
      │
      ▼
Train Model
      │
      ▼
Evaluate Results
```

---

# 14. Mini Project

Create a Student Performance Dashboard.

Tasks:

- Plot marks using a bar chart.
- Plot attendance using a line graph.
- Show marks distribution using a histogram.
- Save all charts as images.

---

# 15. Interview Questions

### What is Matplotlib?

A Python library for creating static, animated, and interactive visualizations.

### Difference between plot() and scatter()?

- plot(): Continuous line graph.
- scatter(): Individual data points.

### Why is visualization important in Machine Learning?

It helps understand data, identify outliers, detect patterns, and communicate findings.

### What does plt.show() do?

It displays the generated figure.

---

# 16. Summary

You learned:

- Why Matplotlib exists.
- Creating line, bar, scatter, histogram, and pie charts.
- Customizing plots.
- Saving figures.
- Real-world AI visualization workflow.

---

# 17. What's Next?

**Lesson 55 – Data Visualization**

You'll learn visualization principles, choosing the right chart, storytelling with data, and avoiding misleading graphs.
