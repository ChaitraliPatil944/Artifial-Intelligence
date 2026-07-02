# Machine Learning - Lesson 8: Training

> **Goal:** Understand what training is, how a model learns from data,
> and the concepts of epochs, batches, iterations, parameters, and
> hyperparameters.

------------------------------------------------------------------------

# 1. What is Training?

Imagine teaching a child to identify cats.

``` text
Show Cat Image
      │
      ▼
Ask: "What is this?"
      │
      ▼
Correct Mistake
      │
      ▼
Child Improves
```

Repeating this process helps the child learn.

Machine Learning training works the same way.

------------------------------------------------------------------------

# 2. Definition

**Training** is the process of teaching a Machine Learning model using
training data so it can discover patterns and make accurate predictions.

------------------------------------------------------------------------

# 3. Training Workflow

``` text
Training Data
      │
      ▼
Learning Algorithm
      │
      ▼
Make Prediction
      │
      ▼
Compare with Correct Label
      │
      ▼
Calculate Error
      │
      ▼
Update Model
      │
      ▼
Repeat
```

This loop continues until the model improves.

------------------------------------------------------------------------

# 4. How Does a Model Learn?

During training the model:

1.  Makes a prediction.
2.  Compares it with the correct answer.
3.  Measures the error.
4.  Adjusts its internal parameters.
5.  Repeats thousands of times.

This gradual improvement is called learning.

------------------------------------------------------------------------

# 5. Parameters

Parameters are values the model **learns automatically** during
training.

Examples:

-   Weights
-   Biases
-   Regression coefficients

The better the parameters, the better the predictions.

------------------------------------------------------------------------

# 6. Hyperparameters

Hyperparameters are values **chosen by the engineer before training**.

Examples:

-   Learning Rate
-   Number of Epochs
-   Batch Size
-   Number of Trees
-   Maximum Tree Depth

Parameters are learned.

Hyperparameters are configured.

------------------------------------------------------------------------

# 7. Epoch

An **Epoch** means the model has seen the **entire training dataset
once**.

Example:

``` text
1000 Samples
     │
     ▼
Model Reads All
     │
     ▼
1 Epoch Completed
```

Training usually requires many epochs.

------------------------------------------------------------------------

# 8. Batch

Instead of processing the whole dataset at once, data is divided into
smaller groups called batches.

Example:

``` text
1000 Samples

├── Batch 1 (100)
├── Batch 2 (100)
├── Batch 3 (100)
...
├── Batch 10 (100)
```

Batches reduce memory usage and speed up training.

------------------------------------------------------------------------

# 9. Iteration

An **Iteration** is one update of the model using one batch.

Example:

``` text
10 Batches
      │
      ▼
10 Iterations
```

If there are 10 batches:

-   1 Epoch = 10 Iterations

------------------------------------------------------------------------

# 10. Complete Training Process

``` text
Training Data
      │
      ▼
Split into Batches
      │
      ▼
Prediction
      │
      ▼
Calculate Error
      │
      ▼
Update Parameters
      │
      ▼
Next Batch
      │
      ▼
Repeat Until All Batches Finished
      │
      ▼
1 Epoch
      │
      ▼
Repeat Multiple Epochs
```

------------------------------------------------------------------------

# 11. Real Industry Example

Email Spam Detection

``` text
Emails
   │
   ▼
Training
   │
   ▼
Model Learns Spam Patterns
   │
   ▼
New Email
   │
   ▼
Spam or Not Spam
```

------------------------------------------------------------------------

# 12. Common Mistakes

❌ Thinking one epoch is enough.

❌ Confusing parameters with hyperparameters.

❌ Assuming training means memorizing data.

A good model learns patterns, not exact examples.

------------------------------------------------------------------------

# 13. Interview Questions

## Basic

**What is training?**

Training is the process of teaching a model using data so it can learn
patterns.

------------------------------------------------------------------------

## Intermediate

**What is the difference between parameters and hyperparameters?**

Parameters are learned during training.

Hyperparameters are set before training.

------------------------------------------------------------------------

## Advanced

**What is the relationship between epochs, batches, and iterations?**

One epoch means processing the entire dataset once.

Each batch produces one iteration.

Iterations per epoch = Number of batches.

------------------------------------------------------------------------

# 14. Memory Map

``` text
                 TRAINING
                     │
      ┌──────────────┼──────────────┐
      │              │              │
 Parameters     Hyperparameters   Epochs
      │              │              │
 Weights      Learning Rate     Full Dataset
 Biases       Batch Size        Once
                     │
                     ▼
                  Batches
                     │
                     ▼
                 Iterations
```

------------------------------------------------------------------------

# Lesson Summary

-   Training teaches a model using data.
-   Models improve by repeatedly correcting their mistakes.
-   Parameters are learned.
-   Hyperparameters are chosen before training.
-   Epoch = One complete pass through the dataset.
-   Batch = Small group of samples.
-   Iteration = One parameter update using one batch.

------------------------------------------------------------------------

# Next Lesson

``` text
Training
    │
    ▼
Trained Model
    │
    ▼
Prediction (Inference)
    │
    ▼
Real-World Deployment
```
