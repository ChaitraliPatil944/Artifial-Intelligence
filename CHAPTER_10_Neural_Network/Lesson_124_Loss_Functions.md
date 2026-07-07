# Chapter 9 -- Neural Networks

# Lesson 124 -- Loss Functions

> **A Loss Function measures how wrong a neural network's prediction is.
> During training, the model continuously adjusts its weights to
> minimize this loss. In simple terms, the loss function is the teacher
> that tells the model how well or badly it is performing.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand what a Loss Function is.
-   Learn why loss functions are essential.
-   Differentiate between Loss and Cost functions.
-   Study common regression and classification loss functions.
-   Learn how to choose the correct loss.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is a Loss Function?
2.  Why Loss Functions?
3.  Loss vs Cost Function
4.  Regression Loss Functions
5.  Classification Loss Functions
6.  Choosing the Right Loss Function
7.  Loss Curves
8.  Python Implementation
9.  Applications
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is a Loss Function?

A loss function measures the error between the model's prediction and
the true value.

``` text
Prediction
     │
Compare with Actual
     │
Loss Function
     │
Error Value
```

Lower loss means better predictions.

------------------------------------------------------------------------

# 2. Why Loss Functions?

Without a loss function, a neural network has no way to know whether its
predictions are improving.

Training loop:

``` text
Predict
   │
Compute Loss
   │
Update Weights
   │
Predict Again
```

------------------------------------------------------------------------

# 3. Loss vs Cost Function

**Loss Function**

-   Error for a **single** training example.

**Cost Function**

-   Average loss across the **entire dataset or batch**.

Although often used interchangeably, this distinction is useful in
interviews.

------------------------------------------------------------------------

# 4. Regression Loss Functions

## Mean Squared Error (MSE)

``` text
Average((Actual - Predicted)²)
```

-   Penalizes large errors heavily.
-   Default for many regression models.

## Mean Absolute Error (MAE)

``` text
Average(|Actual - Predicted|)
```

-   Easier to interpret.
-   Less sensitive to outliers.

## Huber Loss

Combines MAE and MSE.

-   Behaves like MSE for small errors.
-   Behaves like MAE for large errors.
-   Robust to outliers.

------------------------------------------------------------------------

# 5. Classification Loss Functions

## Binary Cross-Entropy

Used for binary classification.

``` text
Output

Spam / Not Spam
```

Typically paired with a **Sigmoid** output.

------------------------------------------------------------------------

## Categorical Cross-Entropy

Used for multi-class classification.

``` text
Cat

Dog

Bird
```

Typically paired with **Softmax**.

------------------------------------------------------------------------

## Sparse Categorical Cross-Entropy

Used when class labels are integers rather than one-hot encoded vectors.

------------------------------------------------------------------------

## Hinge Loss

Used mainly with Support Vector Machines (SVMs).

------------------------------------------------------------------------

# 6. Choosing the Right Loss Function

  Problem                      Output Activation   Recommended Loss
  ---------------------------- ------------------- ----------------------------------
  Regression                   Linear              MSE / MAE / Huber
  Binary Classification        Sigmoid             Binary Cross-Entropy
  Multi-Class Classification   Softmax             Categorical Cross-Entropy
  Integer Class Labels         Softmax             Sparse Categorical Cross-Entropy
  SVM                          Linear              Hinge Loss

------------------------------------------------------------------------

# 7. Loss Curves

A healthy training process:

``` text
Loss ↑

\
 \
  \
   \_____

Epochs →
```

Signs:

-   Steadily decreasing loss → Learning.
-   Flat loss → Underfitting or poor learning rate.
-   Training loss decreases while validation loss rises → Overfitting.

------------------------------------------------------------------------

# 8. Python Implementation

``` python
from tensorflow.keras import Sequential
from tensorflow.keras.layers import Dense

model = Sequential([
    Dense(32, activation="relu"),
    Dense(1, activation="sigmoid")
])

model.compile(
    optimizer="adam",
    loss="binary_crossentropy",
    metrics=["accuracy"]
)
```

Examples of other losses:

``` python
loss="mse"
loss="mae"
loss="categorical_crossentropy"
loss="sparse_categorical_crossentropy"
loss="huber"
```

------------------------------------------------------------------------

# 9. Applications

-   House price prediction
-   Image classification
-   Sentiment analysis
-   Medical diagnosis
-   Speech recognition
-   Large Language Models

------------------------------------------------------------------------

# 10. Mini Project

1.  Train a regression model using MSE.
2.  Replace MSE with MAE.
3.  Compare training curves.
4.  Train a binary classifier using Binary Cross-Entropy.
5.  Compare the effect of different loss functions.

------------------------------------------------------------------------

# 11. Interview Questions

### What is a loss function?

A mathematical function that measures prediction error.

### Difference between loss and cost?

Loss is for one sample, while cost is the average over multiple samples.

### Which loss is used for binary classification?

Binary Cross-Entropy.

### Which loss is commonly used for regression?

Mean Squared Error (MSE).

------------------------------------------------------------------------

# 12. Summary

You learned:

-   What loss functions are.
-   Loss vs cost.
-   MSE, MAE, Huber.
-   Binary and categorical cross-entropy.
-   Choosing the right loss.
-   Python implementation.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 125 -- Backpropagation**

You'll learn how neural networks learn by propagating errors backward
through the network, understand gradients, the chain rule, weight
updates, and why backpropagation made deep learning practical.
