# Chapter 4 – Python for AI

# Lesson 56 – Seaborn

> **Seaborn makes statistical visualization simple, elegant, and informative. It is built on top of Matplotlib and is one of the most widely used libraries in Data Science and AI.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Seaborn is.
- Learn why Seaborn was created.
- Compare Seaborn with Matplotlib.
- Create statistical visualizations.
- Build heatmaps, pair plots, box plots, and violin plots.
- Prepare for Seaborn interview questions.

---

# Table of Contents

1. What is Seaborn?
2. Why Seaborn was Created
3. Installing Seaborn
4. Seaborn vs Matplotlib
5. Loading Built-in Datasets
6. Scatter Plot
7. Line Plot
8. Bar Plot
9. Histogram
10. Box Plot
11. Violin Plot
12. Pair Plot
13. Heatmap
14. Customizing Charts
15. Real-World AI Applications
16. Mini Project
17. Interview Questions
18. Summary
19. What's Next?

---

# 1. What is Seaborn?

Seaborn is a high-level Python visualization library built on top of Matplotlib.

```python
import seaborn as sns
```

It focuses on beautiful statistical graphics with very little code.

---

# 2. Why Seaborn was Created

Matplotlib is powerful but requires more code.

Seaborn provides attractive default styles and advanced statistical plots that would otherwise require significant customization.

---

# 3. Installing Seaborn

```bash
pip install seaborn
```

Import:

```python
import seaborn as sns
import matplotlib.pyplot as plt
```

---

# 4. Seaborn vs Matplotlib

| Matplotlib | Seaborn |
|------------|----------|
| Low-level plotting | High-level statistical plots |
| More customization | Better defaults |
| More code | Less code |
| General purpose | Data Science & AI |

---

# 5. Loading Built-in Datasets

```python
tips = sns.load_dataset("tips")

print(tips.head())
```

Useful datasets:

- tips
- iris
- penguins
- titanic

---

# 6. Scatter Plot

```python
sns.scatterplot(data=tips, x="total_bill", y="tip")
plt.show()
```

Used to study relationships between numerical variables.

---

# 7. Line Plot

```python
sns.lineplot(data=tips, x="size", y="tip")
plt.show()
```

Useful for trends.

---

# 8. Bar Plot

```python
sns.barplot(data=tips, x="day", y="total_bill")
plt.show()
```

Compares averages across categories.

---

# 9. Histogram

```python
sns.histplot(data=tips, x="total_bill", bins=20)
plt.show()
```

Shows how data is distributed.

---

# 10. Box Plot

```python
sns.boxplot(data=tips, x="day", y="total_bill")
plt.show()
```

ASCII

```
|----[====]----|
       *
```

Excellent for detecting outliers.

---

# 11. Violin Plot

```python
sns.violinplot(data=tips, x="day", y="total_bill")
plt.show()
```

A violin plot combines a box plot with the probability distribution of the data.

---

# 12. Pair Plot

```python
iris = sns.load_dataset("iris")

sns.pairplot(iris)
plt.show()
```

Pair plots compare every numerical feature against every other feature.

Frequently used during Exploratory Data Analysis (EDA).

---

# 13. Heatmap

```python
corr = tips.corr(numeric_only=True)

sns.heatmap(corr, annot=True, cmap="coolwarm")
plt.show()
```

Heatmaps visualize correlation matrices.

ASCII

```
      A   B   C

A    ██ ▓▓ ░░
B    ▓▓ ██ ▓▓
C    ░░ ▓▓ ██
```

---

# 14. Customizing Charts

```python
sns.set_style("whitegrid")

sns.barplot(data=tips, x="day", y="tip")

plt.title("Average Tips")

plt.xlabel("Day")

plt.ylabel("Tip")
```

Popular styles:

- white
- dark
- whitegrid
- darkgrid
- ticks

---

# 15. Real-World AI Applications

Seaborn is commonly used for:

- Exploratory Data Analysis
- Correlation analysis
- Feature selection
- Detecting outliers
- Understanding class imbalance
- Presenting ML insights

Typical workflow

```
Dataset
   │
   ▼
Pandas
   │
   ▼
Seaborn
   │
   ▼
Understand Data
   │
   ▼
Train Model
```

---

# 16. Mini Project

Using the Titanic dataset:

- Load the dataset.
- Plot passenger age distribution.
- Compare survival by gender.
- Create a correlation heatmap.
- Write five observations from your visualizations.

---

# 17. Interview Questions

### What is Seaborn?

A statistical visualization library built on top of Matplotlib.

### Why use Seaborn instead of Matplotlib?

It provides better default aesthetics and specialized statistical plots with less code.

### What is a pair plot?

A grid of scatter plots showing relationships among all numerical variables.

### Why are heatmaps useful?

They help visualize correlations and identify strongly related features.

---

# 18. Summary

You learned:

- Why Seaborn exists
- Seaborn vs Matplotlib
- Statistical visualizations
- Pair plots
- Heatmaps
- Box plots
- Violin plots
- AI applications

---

# 19. What's Next?

**Lesson 57 – Jupyter Notebook**

You'll learn why Jupyter Notebook became the standard development environment for data scientists, AI engineers, and researchers, and how to build interactive notebooks for experimentation.
