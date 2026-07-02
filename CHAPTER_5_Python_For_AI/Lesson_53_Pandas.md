# Chapter 4 – Python for AI

# Lesson 53 – Pandas

> **Pandas is the Swiss Army knife of data analysis. Before an AI model can learn, someone has to clean the data. Pandas is the tool that does that job.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Pandas is and why it was created.
- Learn the difference between Series and DataFrame.
- Load, inspect, filter, and manipulate datasets.
- Handle rows and columns efficiently.
- Perform basic statistical analysis.
- Understand why Pandas is used in almost every Machine Learning project.

---

# Table of Contents

1. What is Pandas?
2. Why Pandas was Created
3. Installing Pandas
4. Series
5. DataFrame
6. Reading Data
7. Exploring Data
8. Selecting Rows and Columns
9. Filtering Data
10. Adding & Removing Columns
11. Sorting Data
12. Handling Missing Values
13. Basic Statistics
14. Saving Data
15. Real-World AI Workflow
16. Mini Project
17. Interview Questions
18. Summary
19. What's Next?

---

# 1. What is Pandas?

Pandas is an open-source Python library used for data manipulation and analysis.

It allows us to work with data stored in tables, spreadsheets, CSV files, SQL databases, and more.

```python
import pandas as pd
```

---

# 2. Why Pandas was Created

Imagine receiving a CSV file with one million customer records.

Without Pandas, you would manually process every row using loops.

With Pandas:

```python
df = pd.read_csv("customers.csv")
```

One line loads the entire dataset.

---

# 3. Installing Pandas

```bash
pip install pandas
```

Import it as:

```python
import pandas as pd
```

---

# 4. Series

A Series is a one-dimensional labeled array.

```python
import pandas as pd

marks = pd.Series([85, 91, 78, 95])
print(marks)
```

ASCII Representation

```
Index   Value
0       85
1       91
2       78
3       95
```

---

# 5. DataFrame

A DataFrame is a two-dimensional table.

```python
data = {
    "Name": ["Alice", "Bob"],
    "Age": [21, 22]
}

df = pd.DataFrame(data)
print(df)
```

Output

```
    Name  Age
0  Alice   21
1    Bob   22
```

---

# 6. Reading Data

```python
df = pd.read_csv("students.csv")
```

Other formats:

```python
pd.read_excel()
pd.read_json()
pd.read_sql()
```

---

# 7. Exploring Data

```python
df.head()

df.tail()

df.info()

df.describe()

df.shape

df.columns
```

These commands help you understand your dataset before analysis.

---

# 8. Selecting Rows and Columns

Select one column:

```python
df["Age"]
```

Multiple columns:

```python
df[["Name", "Age"]]
```

Using loc:

```python
df.loc[0]
```

Using iloc:

```python
df.iloc[0]
```

---

# 9. Filtering Data

```python
df[df["Age"] > 21]
```

Multiple conditions:

```python
df[(df["Age"] > 20) & (df["Marks"] > 80)]
```

---

# 10. Adding & Removing Columns

Add:

```python
df["Passed"] = True
```

Remove:

```python
df.drop("Passed", axis=1)
```

---

# 11. Sorting Data

```python
df.sort_values("Age")
```

Descending:

```python
df.sort_values("Marks", ascending=False)
```

---

# 12. Handling Missing Values

Check:

```python
df.isnull().sum()
```

Remove:

```python
df.dropna()
```

Fill:

```python
df.fillna(0)
```

---

# 13. Basic Statistics

```python
df.mean(numeric_only=True)

df.max(numeric_only=True)

df.min(numeric_only=True)

df.median(numeric_only=True)
```

These operations are heavily used before training machine learning models.

---

# 14. Saving Data

```python
df.to_csv("cleaned_data.csv", index=False)
```

---

# 15. Real-World AI Workflow

```
CSV Dataset
      │
      ▼
Read using Pandas
      │
      ▼
Explore Data
      │
      ▼
Clean Missing Values
      │
      ▼
Feature Engineering
      │
      ▼
Train ML Model
```

Almost every supervised learning project starts with this workflow.

---

# 16. Mini Project

Create a Student Performance Analyzer.

Tasks:

- Read a CSV file.
- Display the first 10 rows.
- Find average marks.
- Find top scorer.
- Count failed students.
- Save the cleaned dataset.

---

# 17. Interview Questions

### What is Pandas?

A Python library for data manipulation and analysis.

### Difference between Series and DataFrame?

- Series: One-dimensional.
- DataFrame: Two-dimensional.

### Difference between loc and iloc?

- `loc` uses labels.
- `iloc` uses integer positions.

### Why is Pandas important in Machine Learning?

Because raw data must be cleaned, transformed, and analyzed before model training.

---

# 18. Summary

You learned:

- What Pandas is.
- Series and DataFrames.
- Reading datasets.
- Filtering and selecting data.
- Handling missing values.
- Basic statistics.
- Saving processed datasets.

---

# 19. What's Next?

**Lesson 54 – Matplotlib**

You'll learn how to visualize data using graphs, understand trends, detect patterns, and communicate insights effectively.
