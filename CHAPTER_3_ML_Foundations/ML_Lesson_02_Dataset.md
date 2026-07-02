# Machine Learning - Lesson 2: Dataset

> **Goal:** Understand what a dataset is, why it is important, its
> components, and how datasets are used to train Machine Learning
> models.

------------------------------------------------------------------------

# 1. Why Do We Need a Dataset?

Imagine a teacher wants to know whether students pass exams.

Looking at **one student** is not enough.

``` text
Student
  │
  ▼
Too little information
```

Looking at **many students** reveals patterns.

``` text
Student 1
Student 2
Student 3
Student 4
Student 5
      │
      ▼
Collection of Information
      │
      ▼
Dataset
```

Machine Learning also needs many examples.

------------------------------------------------------------------------

# 2. Definition

A **Dataset** is a collection of related data organized so that a
computer can analyze it.

Think of a dataset as a **book**.

``` text
Book
 ├── Page 1
 ├── Page 2
 ├── Page 3

Dataset
 ├── Row 1
 ├── Row 2
 ├── Row 3
```

------------------------------------------------------------------------

# 3. Data vs Dataset

``` text
Data
 │
 ▼
One piece of information

Example:
Age = 25
```

``` text
Dataset
 │
 ▼
Collection of many pieces of related data

Example:
Name | Age | Salary
```

------------------------------------------------------------------------

# 4. Structure of a Dataset

  Name      Age   Experience   Salary
  ------- ----- ------------ --------
  Alice      24            2    30000
  Bob        28            5    55000
  Carol      31            8    80000

Rows are called **samples (records)**.

Columns are called **features**.

------------------------------------------------------------------------

# 5. Real-World Dataset Examples

## Hospital

  Patient     Age   Blood Pressure Disease
  --------- ----- ---------------- ---------

Purpose: Predict diseases.

------------------------------------------------------------------------

## Banking

| Customer \| Income \| Transactions \| Fraud? \|

Purpose: Detect fraud.

------------------------------------------------------------------------

## Netflix

| User \| Movie \| Rating \| Watch Time \|

Purpose: Recommend movies.

------------------------------------------------------------------------

## Agriculture

| Leaf Image \| Moisture \| Temperature \| Disease \|

Purpose: Detect crop diseases.

------------------------------------------------------------------------

# 6. Types of Datasets

## Structured

``` text
Excel
SQL Table
CSV
```

------------------------------------------------------------------------

## Semi-Structured

``` json
{
  "name":"Alice",
  "city":"Pune"
}
```

Examples: - JSON - XML

------------------------------------------------------------------------

## Unstructured

-   Images
-   Videos
-   Audio
-   PDFs
-   Social media posts

------------------------------------------------------------------------

# 7. Common Dataset Formats

``` text
CSV
Excel (.xlsx)
SQL Database
JSON
Images
Audio
Video
Text Files
```

------------------------------------------------------------------------

# 8. Where Do Companies Get Datasets?

``` text
            Dataset
               │
 ┌─────────────┼──────────────┐
 │             │              │
Users      Sensors      Public Sources
 │             │              │
Apps        IoT        Government Data
Websites    Cameras    Research Datasets
```

------------------------------------------------------------------------

# 9. Public Machine Learning Datasets

Popular sources include:

-   Kaggle
-   UCI Machine Learning Repository
-   Google Dataset Search
-   Government Open Data Portals

------------------------------------------------------------------------

# 10. Why Large Datasets Matter

``` text
10 Images
   │
Poor Learning

100,000 Images
   │
Better Pattern Learning
```

More data often helps, but only if it is relevant and high quality.

------------------------------------------------------------------------

# 11. Good Dataset Characteristics

A good dataset should be:

-   Accurate
-   Balanced
-   Representative
-   Clean
-   Up-to-date
-   Diverse

------------------------------------------------------------------------

# 12. Common Problems

❌ Missing values

❌ Duplicate records

❌ Wrong labels

❌ Imbalanced classes

❌ Noise

These problems reduce model performance.

------------------------------------------------------------------------

# 13. Interview Questions

## Basic

**What is a dataset?**

A dataset is a collection of related data used for analysis or Machine
Learning.

------------------------------------------------------------------------

## Intermediate

**Why is a dataset important?**

Machine Learning models learn patterns from datasets. Without enough
quality data, models cannot generalize well.

------------------------------------------------------------------------

## Advanced

**Is a larger dataset always better?**

No. A smaller, clean, representative dataset can outperform a huge noisy
dataset.

------------------------------------------------------------------------

# 14. Memory Map

``` text
                    DATASET
                       │
      ┌────────────────┼────────────────┐
      │                │                │
 Collection      Many Samples      Many Features
      │                │                │
 CSV            Records/Rows      Columns
 Images          Examples         Attributes
 SQL             Observations     Variables
```

------------------------------------------------------------------------

# Lesson Summary

-   A dataset is a collection of related data.
-   Rows represent samples or records.
-   Columns represent features.
-   Datasets can be structured, semi-structured, or unstructured.
-   High-quality datasets are the foundation of successful Machine
    Learning.

------------------------------------------------------------------------

# Next Lesson

``` text
Dataset
   │
   ▼
Sample
   │
   ▼
Feature
   │
   ▼
Label
```
