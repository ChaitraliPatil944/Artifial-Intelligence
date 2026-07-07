# Chapter 10 -- Convolutional Neural Networks (CNNs)

# Lesson 140 -- Transfer Learning & Fine-Tuning

> **Transfer Learning is the process of reusing a neural network that
> has already been trained on a large dataset for a new task. Instead of
> learning everything from scratch, the model starts with useful visual
> knowledge and adapts it to a specific problem, dramatically reducing
> training time and data requirements.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Transfer Learning.
-   Learn why pretrained models work.
-   Differentiate Feature Extraction and Fine-Tuning.
-   Understand ImageNet.
-   Learn freezing and unfreezing layers.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Transfer Learning?
2.  Why Transfer Learning?
3.  ImageNet
4.  Pretrained Models
5.  Feature Extraction vs Fine-Tuning
6.  Freezing vs Unfreezing Layers
7.  Workflow
8.  Choosing the Right Model
9.  Common Mistakes
10. TensorFlow Implementation
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is Transfer Learning?

Instead of training from random weights:

``` text
Random Weights
      │
Millions of Images
      │
Useful Model
```

Transfer Learning starts with an already trained model.

``` text
Pretrained Model
      │
Your Dataset
      │
Fine-Tuned Model
```

------------------------------------------------------------------------

# 2. Why Transfer Learning?

Benefits:

-   Faster training
-   Less labeled data
-   Better accuracy
-   Lower computational cost

Training a large CNN from scratch can take days or weeks. Reusing
learned features is usually far more practical.

------------------------------------------------------------------------

# 3. ImageNet

ImageNet contains millions of labeled images across 1,000 categories.

Models trained on ImageNet learn generic visual features such as:

-   Edges
-   Textures
-   Shapes
-   Object parts

These features transfer well to many tasks.

------------------------------------------------------------------------

# 4. Pretrained Models

Common choices:

  Model          Best For
  -------------- -----------------------
  VGG16          Simplicity
  ResNet50       General purpose
  MobileNetV2    Mobile devices
  EfficientNet   Accuracy + efficiency

------------------------------------------------------------------------

# 5. Feature Extraction vs Fine-Tuning

### Feature Extraction

``` text
Freeze Backbone
        │
Train New Classifier
```

-   Fast
-   Small datasets
-   Few trainable parameters

### Fine-Tuning

``` text
Unfreeze Upper Layers
         │
Train Again
```

-   Better accuracy
-   Requires more computation
-   Larger datasets preferred

------------------------------------------------------------------------

# 6. Freezing vs Unfreezing Layers

Frozen layers:

-   Weights remain unchanged.
-   Preserve learned features.

Unfrozen layers:

-   Continue learning.
-   Adapt to the new dataset.

Typical strategy:

``` text
Load Pretrained Model
        │
Freeze All Layers
        │
Train Classifier
        │
Unfreeze Top Layers
        │
Fine-Tune
```

------------------------------------------------------------------------

# 7. Workflow

``` text
Choose Pretrained Model
        │
Load ImageNet Weights
        │
Replace Output Layer
        │
Train Classifier
        │
Fine-Tune
        │
Evaluate
```

------------------------------------------------------------------------

# 8. Choosing the Right Model

  Situation              Recommended Model
  ---------------------- -------------------
  Small device           MobileNet
  Highest accuracy       EfficientNet
  Balanced performance   ResNet50
  Learning CNN basics    VGG16

------------------------------------------------------------------------

# 9. Common Mistakes

-   Fine-tuning the whole network immediately.
-   Using a high learning rate.
-   Forgetting to preprocess images correctly.
-   Training on too little data without augmentation.

------------------------------------------------------------------------

# 10. TensorFlow Implementation

``` python
from tensorflow.keras.applications import ResNet50
from tensorflow.keras.layers import GlobalAveragePooling2D, Dense
from tensorflow.keras.models import Sequential

base = ResNet50(
    weights="imagenet",
    include_top=False,
    input_shape=(224,224,3)
)

base.trainable = False

model = Sequential([
    base,
    GlobalAveragePooling2D(),
    Dense(10, activation="softmax")
])
```

To fine-tune:

``` python
base.trainable = True
```

------------------------------------------------------------------------

# 11. Mini Project

1.  Load a pretrained ResNet50.
2.  Freeze the backbone.
3.  Replace the classifier.
4.  Train on a custom image dataset.
5.  Unfreeze the top layers and fine-tune.

------------------------------------------------------------------------

# 12. Interview Questions

### What is Transfer Learning?

Reusing a pretrained model for a new task.

### Difference between Feature Extraction and Fine-Tuning?

Feature Extraction keeps pretrained weights fixed, while Fine-Tuning
updates selected pretrained layers.

### Why is ImageNet important?

It provides large-scale visual knowledge that transfers to many vision
tasks.

### When should you fine-tune?

After training a new classifier, especially if you have sufficient
labeled data.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   Transfer Learning.
-   ImageNet.
-   Pretrained models.
-   Feature Extraction.
-   Fine-Tuning.
-   Freezing and unfreezing layers.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 141 -- Image Augmentation**

You'll learn how image augmentation artificially expands datasets using
transformations such as rotation, flipping, zooming, cropping, and color
changes to improve model generalization and reduce overfitting.
