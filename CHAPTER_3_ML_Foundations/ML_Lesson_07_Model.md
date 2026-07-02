# Machine Learning - Lesson 7: Model

> **Goal:** Understand what a Machine Learning model is, how it is
> created, what it contains, and how it makes predictions.

------------------------------------------------------------------------

# 1. The Biggest Question

People often say:

> "Train the model."

But what is the **model**?

Is it:

-   Python code? ❌
-   CSV file? ❌
-   Magic? Definitely not.
-   Learned mathematical relationships? ✅

------------------------------------------------------------------------

# 2. Child Analogy

Imagine teaching a child to identify apples.

``` text
Apple
Apple
Apple
Apple
      │
      ▼
Child Learns Pattern
      │
      ▼
Recognizes New Apple
```

The child's memory is like a **model**.

The child no longer memorizes every apple. Instead, the child learns a
pattern.

------------------------------------------------------------------------

# 3. Definition

A **Machine Learning Model** is the result of training an algorithm on
data.

It contains the learned mathematical patterns that are used to make
predictions on new data.

------------------------------------------------------------------------

# 4. How Is a Model Created?

``` text
Training Data
      │
      ▼
Learning Algorithm
      │
      ▼
Learns Patterns
      │
      ▼
Machine Learning Model
```

The algorithm learns.

The model is the final result.

------------------------------------------------------------------------

# 5. Algorithm vs Model

Algorithm:

``` text
Recipe
```

Model:

``` text
Finished Cake
```

The recipe tells you **how** to bake.

The cake is the finished product.

Likewise,

-   Algorithm = Learning procedure
-   Model = Learned knowledge

------------------------------------------------------------------------

# 6. What Does a Model Contain?

It depends on the algorithm.

Linear Regression:

-   Coefficients
-   Intercept

Decision Tree:

-   Tree structure
-   Split conditions

Neural Network:

-   Weights
-   Biases

The common idea is the same:

The model stores what it learned.

------------------------------------------------------------------------

# 7. Prediction Using a Model

``` text
New Data
    │
    ▼
Saved Model
    │
    ▼
Prediction
```

The model applies learned patterns to unseen data.

------------------------------------------------------------------------

# 8. Real Example

House Price Prediction

Training:

``` text
Area
Bedrooms
Location
      │
      ▼
Model Learns
```

Prediction:

``` text
New House
     │
     ▼
Model
     │
     ▼
₹75,00,000
```

------------------------------------------------------------------------

# 9. Saving a Model

After training, companies usually save the model.

``` text
Training
    │
    ▼
Model
    │
    ▼
Save (.pkl, .joblib, etc.)
    │
    ▼
Reuse Later
```

The model does not need retraining every time.

------------------------------------------------------------------------

# 10. Industry Example

Fraud Detection

``` text
Past Transactions
      │
      ▼
Train Model
      │
      ▼
Saved Model
      │
      ▼
New Transaction
      │
      ▼
Fraud?
```

Hospitals, banks, recommendation engines, and search systems follow a
similar pattern.

------------------------------------------------------------------------

# 11. Common Mistakes

❌ Confusing algorithm with model.

❌ Thinking the model is only Python code.

❌ Believing the model memorizes every sample.

A good model learns patterns, not exact copies of the data.

------------------------------------------------------------------------

# 12. Interview Questions

## Basic

**What is a Machine Learning model?**

A trained mathematical representation that has learned patterns from
data and can make predictions.

------------------------------------------------------------------------

## Intermediate

**What is the difference between an algorithm and a model?**

An algorithm is the learning method. A model is the output produced
after training.

------------------------------------------------------------------------

## Advanced

**Why do we save models?**

Training can be expensive. Saving a trained model allows predictions
without repeating training.

------------------------------------------------------------------------

# 13. Memory Map

``` text
                 TRAINING DATA
                       │
                       ▼
                 LEARNING ALGORITHM
                       │
                 Learns Patterns
                       ▼
                     MODEL
                       │
                 Stored Knowledge
                       ▼
                  NEW DATA
                       │
                       ▼
                  PREDICTION
```

------------------------------------------------------------------------

# Lesson Summary

-   A model is the result of training.
-   The model stores learned mathematical patterns.
-   Algorithms create models.
-   Models make predictions on unseen data.
-   Models are often saved and deployed to production.

------------------------------------------------------------------------

# Next Lesson

``` text
Training
    │
    ▼
Learning
    │
    ▼
Prediction (Inference)
```
