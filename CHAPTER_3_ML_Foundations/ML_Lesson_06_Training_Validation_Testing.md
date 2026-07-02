# Machine Learning - Lesson 6: Training Data, Validation Data, and Testing Data

> **Goal:** Understand why datasets are split, how each split is used,
> and why this process is critical for building reliable Machine
> Learning models.

------------------------------------------------------------------------

# 1. Why Can't We Use One Dataset for Everything?

Imagine a student memorizes every question from last year's exam.

On the same paper:

``` text
Exam Questions
      │
      ▼
100% Marks
```

Does that prove the student understands the subject?

**No.**

They may have simply memorized the answers.

Machine Learning models can make the same mistake.

------------------------------------------------------------------------

# 2. The Problem: Memorization

``` text
Dataset
   │
   ▼
Model Memorizes Answers
   │
   ▼
Looks Accurate
```

When new data arrives:

``` text
New Data
   │
   ▼
Wrong Predictions
```

This is called **Overfitting**.

------------------------------------------------------------------------

# 3. The Solution

Split the dataset.

``` text
                 Dataset
                    │
     ┌──────────────┼──────────────┐
     │              │              │
 Training      Validation      Testing
```

Each part has a different purpose.

------------------------------------------------------------------------

# 4. Training Data

Training data teaches the model.

``` text
Training Data
      │
      ▼
Model Learns Patterns
```

Usually 60-80% of the dataset.

Example:

1000 samples

-   800 → Training

------------------------------------------------------------------------

# 5. Validation Data

Validation data helps improve the model while training.

``` text
Training
   │
   ▼
Validation
   │
   ▼
Adjust Model
```

Used to compare models and tune settings (hyperparameters).

Usually 10-20%.

------------------------------------------------------------------------

# 6. Testing Data

Testing data is never shown during training.

``` text
Unseen Data
     │
     ▼
Model
     │
     ▼
Final Performance
```

Usually 10-20%.

This is the final exam.

------------------------------------------------------------------------

# 7. School Analogy

``` text
Class Notes
      │
      ▼
Training

Practice Test
      │
      ▼
Validation

Final Exam
      │
      ▼
Testing
```

A student who performs well only on class notes has not truly learned.

------------------------------------------------------------------------

# 8. Typical Split

``` text
Dataset (100%)

│
├── 70% Training
├── 15% Validation
└── 15% Testing
```

Other common splits:

-   80 / 10 / 10
-   60 / 20 / 20

There is no universal rule.

------------------------------------------------------------------------

# 9. Complete Workflow

``` text
Dataset
   │
   ▼
Split Dataset
   │
   ├── Training
   ├── Validation
   └── Testing
        │
        ▼
Train Model
        │
        ▼
Tune Model
        │
        ▼
Final Evaluation
```

------------------------------------------------------------------------

# 10. Why Testing Data Must Remain Hidden

If the model repeatedly sees the testing data, the final evaluation
becomes unfair.

``` text
Seen Test Data
      │
      ▼
Biased Evaluation
```

Testing data should simulate real-world unseen data.

------------------------------------------------------------------------

# 11. Real Industry Example

Fraud Detection

``` text
Old Transactions
      │
      ▼
Training

Recent Transactions
      │
      ▼
Validation

Newest Unseen Transactions
      │
      ▼
Testing
```

Companies care about how the model performs on future data, not past
data.

------------------------------------------------------------------------

# 12. Common Mistakes

❌ Training and testing on the same dataset.

❌ Looking at testing results while improving the model.

❌ Ignoring validation data.

------------------------------------------------------------------------

# 13. Interview Questions

## Basic

**What is training data?**

Training data is used to teach the model patterns.

------------------------------------------------------------------------

## Intermediate

**Why do we split datasets?**

To evaluate how well a model generalizes to unseen data.

------------------------------------------------------------------------

## Advanced

**What is the purpose of validation data?**

Validation data helps tune hyperparameters and select the best model
without using the test set.

------------------------------------------------------------------------

# 14. Memory Map

``` text
                   DATASET
                      │
      ┌───────────────┼───────────────┐
      │               │               │
 Training       Validation        Testing
      │               │               │
 Learn        Improve Model     Final Evaluation
```

------------------------------------------------------------------------

# Lesson Summary

-   Training data teaches the model.
-   Validation data improves and tunes the model.
-   Testing data measures final performance.
-   Testing data must remain unseen during training.
-   Proper dataset splitting helps prevent overfitting.

------------------------------------------------------------------------

# Next Lesson

``` text
Dataset
   │
   ▼
Training
   │
   ▼
Model
   │
   ▼
Prediction (Inference)
```
