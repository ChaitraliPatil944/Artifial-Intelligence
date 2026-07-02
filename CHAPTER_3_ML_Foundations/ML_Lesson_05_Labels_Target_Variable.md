# Machine Learning - Lesson 5: Labels (Target Variable)

> **Goal:** Understand what labels are, why they are needed, how they
> differ from features, and how they are used in Machine Learning.

------------------------------------------------------------------------

# 1. Why Do We Need Labels?

Imagine a teacher gives students question papers but never tells them
the correct answers.

``` text
Question
   │
   ▼
No Correct Answer
   │
   ▼
No Learning
```

To learn, students need the correct answer.

Machine Learning is similar.

The correct answer is called the **Label**.

------------------------------------------------------------------------

# 2. Definition

A **Label** (also called the **Target Variable**) is the correct output
that a Machine Learning model tries to predict.

Features = Inputs

Label = Desired Output

------------------------------------------------------------------------

# 3. Child Analogy

Imagine teaching a child fruits.

``` text
Round
Red
Sweet
   │
   ▼
Apple
```

The characteristics are **Features**.

The name **Apple** is the **Label**.

------------------------------------------------------------------------

# 4. Features vs Labels

  Hours Studied     Attendance   Previous Marks Pass
  --------------- ------------ ---------------- ------
  2                         60               45 No
  5                         85               78 Yes
  7                         95               88 Yes

Features:

-   Hours Studied
-   Attendance
-   Previous Marks

Label:

-   Pass

------------------------------------------------------------------------

# 5. Visual Flow

``` text
Features
(Hours, Attendance, Marks)
           │
           ▼
   Machine Learning Model
           │
           ▼
       Prediction
        (Pass?)
```

During training, the model compares its prediction with the real label.

------------------------------------------------------------------------

# 6. Why Are Labels Important?

Without labels, a supervised learning model cannot know whether its
prediction is correct.

``` text
Prediction
     │
     ▼
Compare with Label
     │
     ▼
Correct Mistakes
     │
     ▼
Learn
```

------------------------------------------------------------------------

# 7. Types of Labels

## Binary Labels

Two possible outputs.

Examples:

-   Yes / No
-   Fraud / Not Fraud
-   Pass / Fail

------------------------------------------------------------------------

## Multi-Class Labels

More than two categories.

Examples:

-   Cat
-   Dog
-   Horse
-   Bird

Only one correct class.

------------------------------------------------------------------------

## Multi-Label

More than one correct answer.

Example:

Photo contains:

-   Dog ✅
-   Person ✅
-   Car ❌

The image has multiple labels.

------------------------------------------------------------------------

## Continuous Labels (Regression)

Examples:

-   House Price
-   Salary
-   Temperature
-   Stock Price

The label is a number instead of a category.

------------------------------------------------------------------------

# 8. Real Industry Examples

## Healthcare

Features: - Age - Blood Pressure - Sugar

Label: Disease

------------------------------------------------------------------------

## Banking

Features: - Amount - Time - Location

Label: Fraud / Not Fraud

------------------------------------------------------------------------

## Agriculture

Features: - Leaf Image - Humidity - Temperature

Label: Healthy / Diseased

------------------------------------------------------------------------

## E-Commerce

Features: - Customer History - Cart Items - Search History

Label: Will Purchase? (Yes / No)

------------------------------------------------------------------------

# 9. Dependent vs Independent Variables

Independent Variables = Features

Dependent Variable = Label

``` text
Features
     │
     ▼
 Influence
     │
     ▼
Label
```

The label depends on the features.

------------------------------------------------------------------------

# 10. Common Mistakes

❌ Using the label as an input feature.

❌ Choosing the wrong column as the target.

❌ Training with incorrect labels.

Poor labels produce poor models.

------------------------------------------------------------------------

# 11. Interview Questions

## Basic

What is a label?

A label is the correct output that a Machine Learning model learns to
predict.

------------------------------------------------------------------------

## Intermediate

What is the difference between a feature and a label?

Features are the inputs to the model. The label is the desired output.

------------------------------------------------------------------------

## Advanced

Can every Machine Learning algorithm use labels?

No. Supervised learning requires labels. Unsupervised learning works
without labels.

------------------------------------------------------------------------

# 12. Memory Map

``` text
                     LABEL
                       │
       ┌───────────────┼───────────────┐
       │               │               │
   Binary         Multi-Class     Continuous
       │               │               │
   Yes/No        Cat, Dog       House Price
 Fraud/Not       Bird, Horse    Temperature
 Pass/Fail
```

------------------------------------------------------------------------

# Lesson Summary

-   Labels are the correct answers the model learns from.
-   Labels are also called target variables.
-   Features are inputs; labels are outputs.
-   Labels can be binary, multi-class, multi-label, or continuous.
-   Correct labels are essential for supervised learning.

------------------------------------------------------------------------

# Next Lesson

``` text
Features
    │
    ▼
Labels
    │
    ▼
Training Data
    │
    ▼
Testing Data
    │
    ▼
Validation Data
```
