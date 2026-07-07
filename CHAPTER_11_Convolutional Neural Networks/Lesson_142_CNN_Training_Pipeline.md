# Chapter 10 -- Convolutional Neural Networks (CNNs)

# Lesson 142 -- CNN Training Pipeline

> **A CNN Training Pipeline is the complete workflow that transforms raw
> image data into a trained, evaluated, and deployable deep learning
> model. A well-designed pipeline ensures reproducibility, better
> accuracy, and efficient experimentation.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand the end-to-end CNN workflow.
-   Learn dataset preparation and preprocessing.
-   Study model training, validation, and evaluation.
-   Learn callbacks and model saving.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  Overview
2.  Dataset Collection
3.  Train/Validation/Test Split
4.  Image Preprocessing
5.  Data Augmentation
6.  Building the CNN
7.  Model Compilation
8.  Training
9.  Validation
10. Callbacks
11. Evaluation
12. Saving & Loading Models
13. End-to-End Pipeline
14. Python Example
15. Mini Project
16. Interview Questions
17. Summary
18. What's Next?

------------------------------------------------------------------------

# 1. Overview

``` text
Collect Data
     │
Preprocess
     │
Augment
     │
Split Dataset
     │
Build CNN
     │
Compile
     │
Train
     │
Validate
     │
Evaluate
     │
Save Model
     │
Deploy
```

------------------------------------------------------------------------

# 2. Dataset Collection

A good dataset should be:

-   Large
-   Diverse
-   Correctly labeled
-   Balanced across classes

Example sources:

-   Kaggle
-   ImageNet
-   CIFAR-10
-   MNIST
-   Custom datasets

------------------------------------------------------------------------

# 3. Train / Validation / Test Split

Typical split:

``` text
70% Training

15% Validation

15% Testing
```

Purpose:

-   **Training:** Learn parameters.
-   **Validation:** Tune hyperparameters.
-   **Testing:** Measure final performance.

------------------------------------------------------------------------

# 4. Image Preprocessing

Common preprocessing steps:

-   Resize images
-   Normalize pixel values
-   Convert color format if needed
-   Remove corrupted images

Example:

``` python
image = image / 255.0
```

------------------------------------------------------------------------

# 5. Data Augmentation

Apply transformations only to the training set.

Examples:

-   Flip
-   Rotate
-   Zoom
-   Crop
-   Brightness adjustment

This improves generalization.

------------------------------------------------------------------------

# 6. Building the CNN

Typical architecture:

``` text
Input
 │
Conv
 │
ReLU
 │
Pooling
 │
Conv
 │
ReLU
 │
Pooling
 │
Flatten
 │
Dense
 │
Output
```

------------------------------------------------------------------------

# 7. Model Compilation

Choose:

-   Optimizer
-   Loss function
-   Evaluation metrics

``` python
model.compile(
    optimizer="adam",
    loss="categorical_crossentropy",
    metrics=["accuracy"]
)
```

------------------------------------------------------------------------

# 8. Training

``` python
history = model.fit(
    train_ds,
    validation_data=val_ds,
    epochs=20
)
```

Training updates weights using:

``` text
Forward Pass
     │
Loss
     │
Backpropagation
     │
Optimizer
```

------------------------------------------------------------------------

# 9. Validation

Validation checks model performance after each epoch.

Benefits:

-   Detect overfitting
-   Tune hyperparameters
-   Support early stopping

------------------------------------------------------------------------

# 10. Callbacks

### Early Stopping

Stops training when validation performance stops improving.

### Model Checkpoint

Saves the best model automatically.

### Learning Rate Scheduler

Reduces the learning rate when progress slows.

Example:

``` python
from tensorflow.keras.callbacks import EarlyStopping

callback = EarlyStopping(
    monitor="val_loss",
    patience=5,
    restore_best_weights=True
)
```

------------------------------------------------------------------------

# 11. Evaluation

Evaluate using:

-   Accuracy
-   Precision
-   Recall
-   F1-score
-   Confusion Matrix
-   ROC-AUC (binary tasks)

``` python
model.evaluate(test_ds)
```

------------------------------------------------------------------------

# 12. Saving & Loading Models

Save:

``` python
model.save("cnn_model.keras")
```

Load:

``` python
from tensorflow.keras.models import load_model

model = load_model("cnn_model.keras")
```

------------------------------------------------------------------------

# 13. End-to-End Pipeline

``` text
Dataset
   │
Cleaning
   │
Preprocessing
   │
Augmentation
   │
Split
   │
CNN
   │
Training
   │
Validation
   │
Evaluation
   │
Save
   │
Inference / Deployment
```

------------------------------------------------------------------------

# 14. Python Example

``` python
model.fit(
    train_ds,
    validation_data=val_ds,
    epochs=20,
    callbacks=[callback]
)

model.evaluate(test_ds)

model.save("cnn.keras")
```

------------------------------------------------------------------------

# 15. Mini Project

1.  Prepare an image dataset.
2.  Build a CNN.
3.  Apply augmentation.
4.  Train with EarlyStopping.
5.  Save the best model.
6.  Evaluate on the test set.

------------------------------------------------------------------------

# 16. Interview Questions

### Why is a validation set needed?

To tune the model and detect overfitting without touching the test set.

### Should augmentation be applied to the test set?

No. Test data should represent unseen real-world samples.

### What does EarlyStopping do?

Stops training when validation performance no longer improves.

### Why save the best model?

To keep the weights with the best validation performance.

------------------------------------------------------------------------

# 17. Summary

You learned:

-   Complete CNN workflow.
-   Dataset preparation.
-   Preprocessing and augmentation.
-   Training and validation.
-   Callbacks.
-   Evaluation.
-   Model persistence.

------------------------------------------------------------------------

# 18. What's Next?

**Lesson 143 -- CNN Project: Image Classification**

You'll build a complete real-world image classification project using
TensorFlow/Keras, covering data loading, augmentation, CNN design,
training, evaluation, visualization, prediction, and model deployment
basics.
