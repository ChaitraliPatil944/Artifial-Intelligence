# Lesson 41: Gradient Descent

> Goal: Understand the algorithm that powers modern AI training.

Gradient Descent repeatedly updates parameters.

``` text
Initialize Weights
        │
        ▼
Predict
        │
        ▼
Calculate Loss
        │
        ▼
Compute Gradient
        │
        ▼
Update Weights
        │
        └───────────────┐
                        ▼
                 Repeat Until Convergence
```

Update Rule:

``` text
New Weight = Old Weight - Learning Rate × Gradient
```

Applications: - Linear Regression - Logistic Regression - CNNs -
Transformers - LLMs

Python:

``` python
w = w - lr * grad
```

Interview: Why learning rate matters?

Too large: diverges. Too small: trains slowly.

Summary: Gradient Descent is the core optimization algorithm behind
machine learning and deep learning.
