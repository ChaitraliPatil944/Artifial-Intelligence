# Machine Learning - Lesson 4: Features

> **Goal:** Understand what features are, why they are important, the
> different types of features, and how they influence Machine Learning
> models.

------------------------------------------------------------------------

# 1. Why Do We Need Features?

Imagine you want to predict whether a student will pass an exam.

Which information would help?

-   Hours Studied ✅
-   Attendance ✅
-   Previous Marks ✅

These pieces of information help make a prediction.

They are called **Features**.

------------------------------------------------------------------------

# 2. Definition

A **Feature** is an individual property, characteristic, or measurable
attribute used by a Machine Learning model to make predictions.

Simply put:

> Features are the **inputs** given to the model.

------------------------------------------------------------------------

# 3. Child Analogy

Imagine identifying a fruit.

``` text
Fruit
 │
 ├── Color
 ├── Size
 ├── Shape
 └── Weight
```

These characteristics help you recognize the fruit.

Similarly, Machine Learning uses features to recognize patterns.

------------------------------------------------------------------------

# 4. Dataset Example

  Hours Studied     Attendance   Previous Marks Pass
  --------------- ------------ ---------------- ------
  2                         60               45 No
  4                         75               60 Yes
  6                         90               82 Yes

Features:

-   Hours Studied
-   Attendance
-   Previous Marks

Label:

-   Pass

------------------------------------------------------------------------

# 5. Features vs Label

``` text
Features
(Hours, Attendance, Marks)
          │
          ▼
   Machine Learning Model
          │
          ▼
      Prediction
        (Pass)
```

Features are inputs.

Label is the desired output.

------------------------------------------------------------------------

# 6. Types of Features

## Numerical

-   Age
-   Salary
-   Height
-   Temperature

------------------------------------------------------------------------

## Categorical

-   Gender
-   City
-   Blood Group
-   Product Category

------------------------------------------------------------------------

## Binary

-   Yes / No
-   True / False
-   Purchased / Not Purchased

------------------------------------------------------------------------

## Text

-   Reviews
-   Emails
-   Chat Messages

------------------------------------------------------------------------

## Image

Every image becomes numerical pixel features.

------------------------------------------------------------------------

## Audio

Voice recordings are converted into numerical features.

------------------------------------------------------------------------

# 7. Real Industry Examples

## Healthcare

Features: - Age - Blood Pressure - Sugar Level

Prediction: Disease

------------------------------------------------------------------------

## Banking

Features: - Transaction Amount - Time - Location

Prediction: Fraud

------------------------------------------------------------------------

## Agriculture

Features: - Leaf Image - Temperature - Humidity

Prediction: Crop Disease

------------------------------------------------------------------------

## Netflix

Features: - Watch History - Ratings - Genres

Prediction: Recommended Movie

------------------------------------------------------------------------

# 8. Good Features

Good features should be:

-   Relevant
-   Informative
-   Consistent
-   Easy to measure
-   Related to the prediction

Poor features confuse the model.

------------------------------------------------------------------------

# 9. Feature Engineering

Sometimes raw features are not enough.

Example:

Date of Birth

↓

Age

Age is often more useful than the raw date.

Creating better features is called **Feature Engineering**.

------------------------------------------------------------------------

# 10. Feature Selection

Not every feature helps.

Example:

Predicting house price.

Useful: - Area - Bedrooms - Location

Not useful: - House owner's favorite color

Removing unnecessary features improves many models.

------------------------------------------------------------------------

# 11. Common Mistakes

❌ Using irrelevant features.

❌ Using duplicate features.

❌ Confusing features with labels.

Remember:

Columns used for prediction = Features.

Column to predict = Label.

------------------------------------------------------------------------

# 12. Interview Questions

## Basic

What is a feature?

A feature is an input variable used by a Machine Learning model to make
predictions.

------------------------------------------------------------------------

## Intermediate

Why are features important?

Features contain the information the model uses to discover patterns.

------------------------------------------------------------------------

## Advanced

What is feature engineering?

Feature engineering is the process of creating, transforming, or
selecting features that improve model performance.

------------------------------------------------------------------------

# 13. Memory Map

``` text
                     FEATURES
                         │
      ┌──────────────────┼──────────────────┐
      │                  │                  │
 Numerical         Categorical         Binary
      │                  │                  │
 Age              City              Yes/No
 Salary           Gender            True/False
 Height           Product Type      Purchased
                         │
                         ▼
               Machine Learning Model
                         │
                         ▼
                    Prediction
```

------------------------------------------------------------------------

# Lesson Summary

-   Features are the input variables of a Machine Learning model.
-   Good features improve predictions.
-   Features can be numerical, categorical, binary, text, image, or
    audio.
-   Feature engineering creates better features.
-   Feature selection removes unnecessary ones.

------------------------------------------------------------------------

# Next Lesson

``` text
Features
    │
    ▼
Label / Target Variable
    │
    ▼
Training Data
```
