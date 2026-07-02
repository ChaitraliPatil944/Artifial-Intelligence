# Machine Learning - Lesson 3: Sample (Observation / Record / Instance)

> **Goal:** Understand what a sample is, why it is important, and how it
> relates to datasets, features, and labels.

------------------------------------------------------------------------

# 1. Why Do We Need Samples?

Imagine a teacher wants to predict whether students will pass an exam.

Looking at one student gives one example.

``` text
Student
  │
  ▼
One Example
```

Looking at 100 students gives 100 examples.

Each example is called a **Sample**.

------------------------------------------------------------------------

# 2. Definition

A **Sample** is one individual example or observation in a dataset.

Other common names:

-   Observation
-   Record
-   Instance
-   Data Point

These terms usually mean the same thing.

------------------------------------------------------------------------

# 3. Child Analogy

Imagine a basket of apples.

``` text
Basket
├── Apple 1
├── Apple 2
├── Apple 3
└── Apple 4
```

The basket is the **dataset**.

Each apple is a **sample**.

------------------------------------------------------------------------

# 4. Sample vs Dataset

``` text
Dataset
│
├── Sample 1
├── Sample 2
├── Sample 3
└── Sample 4
```

Dataset = Collection

Sample = One member of that collection

------------------------------------------------------------------------

# 5. Example Dataset

  Name      Age   Experience   Salary
  ------- ----- ------------ --------
  Alice      24            2    30000
  Bob        28            5    55000
  Carol      31            8    80000

Here:

-   Dataset = Entire table
-   Sample = One row
-   Feature = One column (Age, Experience)
-   Salary may be the target depending on the problem.

------------------------------------------------------------------------

# 6. Sample in Different Domains

## Image Classification

``` text
Dataset
├── Cat Image
├── Dog Image
├── Bird Image
```

Each image = One sample

------------------------------------------------------------------------

## Healthcare

Each patient record = One sample

------------------------------------------------------------------------

## Banking

Each transaction = One sample

------------------------------------------------------------------------

## Agriculture

Each leaf image = One sample

------------------------------------------------------------------------

# 7. Why Many Samples Matter

``` text
5 Samples
   │
Poor Learning

50,000 Samples
   │
Better Learning
```

More representative samples usually improve learning.

Quality still matters.

------------------------------------------------------------------------

# 8. Samples During Training

``` text
Dataset
   │
   ▼
Sample 1
Sample 2
Sample 3
Sample 4
   │
   ▼
Model Learns
```

The model learns by processing many samples.

------------------------------------------------------------------------

# 9. Common Mistakes

❌ Thinking one sample is a dataset.

❌ Confusing rows with columns.

Remember:

-   Row = Sample
-   Column = Feature

------------------------------------------------------------------------

# 10. Interview Questions

## Basic

What is a sample?

A sample is one individual observation or record in a dataset.

------------------------------------------------------------------------

## Intermediate

What is the difference between a sample and a dataset?

A dataset is a collection of samples. A sample is a single example
within that collection.

------------------------------------------------------------------------

## Advanced

Why is sample diversity important?

A diverse set of samples helps the model learn patterns that generalize
to new, unseen data instead of memorizing only a narrow subset.

------------------------------------------------------------------------

# 11. Memory Map

``` text
                   DATASET
                      │
      ┌───────────────┼───────────────┐
      │               │               │
  Sample 1        Sample 2       Sample 3
      │               │               │
 Features        Features       Features
```

------------------------------------------------------------------------

# Lesson Summary

-   A sample is one row in a dataset.
-   Sample, observation, record, instance, and data point are commonly
    interchangeable.
-   A dataset contains many samples.
-   Machine Learning models learn by processing many samples.

------------------------------------------------------------------------

# Next Lesson

``` text
Dataset
   │
   ▼
Sample
   │
   ▼
Features
   │
   ▼
Labels
```
