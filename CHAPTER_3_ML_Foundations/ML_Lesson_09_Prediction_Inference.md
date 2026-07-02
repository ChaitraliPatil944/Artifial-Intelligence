# Machine Learning - Lesson 9: Prediction (Inference)

> **Goal:** Understand what inference is, how a trained model makes
> predictions, and how inference is used in real-world AI systems.

------------------------------------------------------------------------

# 1. The Journey So Far

``` text
Data
  │
  ▼
Dataset
  │
  ▼
Training
  │
  ▼
Model
```

Now comes the real purpose of Machine Learning:

``` text
New Data
   │
   ▼
Prediction
```

------------------------------------------------------------------------

# 2. What is Prediction?

Imagine you teach a child to identify apples.

After weeks of practice, you show a **new fruit**.

``` text
New Fruit
    │
    ▼
Child Says
"It's an Apple!"
```

The child is using previous learning.

Machine Learning does the same thing.

------------------------------------------------------------------------

# 3. Definition

**Prediction** (also called **Inference**) is the process of using a
trained Machine Learning model to make predictions on new, unseen data.

Training = Learning

Inference = Using what was learned

------------------------------------------------------------------------

# 4. Training vs Inference

``` text
TRAINING

Training Data
      │
      ▼
Learn Patterns
      │
      ▼
Create Model


INFERENCE

New Data
    │
    ▼
Trained Model
    │
    ▼
Prediction
```

Training happens once (or occasionally).

Inference may happen millions of times every day.

------------------------------------------------------------------------

# 5. Step-by-Step Inference

``` text
New Customer Data
        │
        ▼
Load Trained Model
        │
        ▼
Extract Features
        │
        ▼
Model Calculates Output
        │
        ▼
Prediction
```

Example:

``` text
Hours Studied = 6
Attendance = 92%

↓

Prediction

Pass
```

------------------------------------------------------------------------

# 6. Why Is Inference Faster?

Training:

``` text
Read Data
Predict
Calculate Error
Update Parameters
Repeat Thousands of Times
```

Inference:

``` text
Read Input
Use Learned Parameters
Return Prediction
```

No learning happens during inference.

------------------------------------------------------------------------

# 7. Types of Inference

## Real-Time (Online)

One request at a time.

Examples:

-   Face Unlock
-   Google Translate
-   Chatbots
-   Fraud Detection

------------------------------------------------------------------------

## Batch Inference

Many predictions together.

Examples:

-   Monthly sales forecast
-   Credit score updates
-   Email categorization

------------------------------------------------------------------------

# 8. Industry Examples

## Netflix

``` text
Watch History
      │
      ▼
Recommendation Model
      │
      ▼
Suggested Movies
```

------------------------------------------------------------------------

## Hospital

``` text
Patient Data
      │
      ▼
Disease Prediction Model
      │
      ▼
Risk Score
```

------------------------------------------------------------------------

## Banking

``` text
New Transaction
       │
       ▼
Fraud Detection Model
       │
       ▼
Fraud / Not Fraud
```

------------------------------------------------------------------------

## Agriculture

``` text
Leaf Image
     │
     ▼
Disease Detection Model
     │
     ▼
Healthy / Diseased
```

------------------------------------------------------------------------

# 9. Deployment

After training:

``` text
Train Model
     │
     ▼
Save Model
     │
     ▼
Deploy to Server
     │
     ▼
Users Send Requests
     │
     ▼
Predictions Returned
```

This is how production AI systems work.

------------------------------------------------------------------------

# 10. Confidence Score

Many models return:

``` text
Prediction:
Cat

Confidence:
97%
```

The confidence indicates how strongly the model believes its prediction.

High confidence does **not** always mean the prediction is correct.

------------------------------------------------------------------------

# 11. Common Mistakes

❌ Thinking inference changes the model.

❌ Believing prediction always means 100% certainty.

❌ Using a model on data very different from the training data.

------------------------------------------------------------------------

# 12. Interview Questions

## Basic

**What is inference?**

Inference is the process of using a trained Machine Learning model to
make predictions on new data.

------------------------------------------------------------------------

## Intermediate

**Why is inference faster than training?**

Because the model only performs calculations using learned parameters.
It does not update them.

------------------------------------------------------------------------

## Advanced

**What is the difference between batch inference and real-time
inference?**

Batch inference processes many records together, while real-time
inference predicts one or a few records immediately after receiving a
request.

------------------------------------------------------------------------

# 13. Memory Map

``` text
                 TRAINED MODEL
                      │
        ┌─────────────┼─────────────┐
        │             │             │
    New Data     Inference     Prediction
        │             │             │
  Features      Fast Process   Result
                      │
                      ▼
             Real-Time / Batch
```

------------------------------------------------------------------------

# Lesson Summary

-   Prediction and inference mean using a trained model on unseen data.
-   Training teaches the model.
-   Inference uses the learned knowledge.
-   Inference is usually much faster than training.
-   Models are commonly deployed as APIs or services for real-world
    applications.

------------------------------------------------------------------------

# Next Lesson

``` text
Complete Machine Learning Workflow

Data
 │
 ▼
Dataset
 │
 ▼
Training
 │
 ▼
Model
 │
 ▼
Inference
 │
 ▼
Evaluation
 │
 ▼
Deployment
```
