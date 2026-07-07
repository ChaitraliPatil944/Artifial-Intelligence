# Chapter 10 -- Convolutional Neural Networks (CNNs)

# Lesson 143 -- CNN Project: Image Classification

> **In this capstone project, you'll build a complete image
> classification system using TensorFlow/Keras. The goal is to combine
> everything learned in this chapter into an industry-style workflow,
> from loading images to making predictions with a trained CNN.**

------------------------------------------------------------------------

# Learning Objectives

-   Build an end-to-end CNN project.
-   Apply preprocessing and augmentation.
-   Design and train a CNN.
-   Evaluate model performance.
-   Save and reuse trained models.
-   Prepare for real-world projects and interviews.

------------------------------------------------------------------------

# Table of Contents

1.  Problem Statement
2.  Dataset
3.  Project Structure
4.  Workflow
5.  Data Loading
6.  Data Preprocessing
7.  Image Augmentation
8.  CNN Model
9.  Training
10. Evaluation
11. Prediction
12. Saving & Loading
13. Best Practices
14. Mini Extensions
15. Interview Questions
16. Summary
17. What's Next?

------------------------------------------------------------------------

# 1. Problem Statement

Build a CNN that classifies images into predefined categories.

Example datasets:

-   Cats vs Dogs
-   CIFAR-10
-   Flowers
-   Fruits-360

------------------------------------------------------------------------

# 2. Dataset

Typical split:

``` text
Train      70%

Validation 15%

Test       15%
```

Images should be resized to a consistent size (for example,
**224×224**).

------------------------------------------------------------------------

# 3. Project Structure

``` text
cnn-image-classifier/
│
├── dataset/
│   ├── train/
│   ├── validation/
│   └── test/
│
├── models/
├── notebooks/
├── train.py
├── predict.py
├── requirements.txt
└── README.md
```

------------------------------------------------------------------------

# 4. Workflow

``` text
Collect Images
      │
Preprocess
      │
Augment
      │
Build CNN
      │
Train
      │
Validate
      │
Evaluate
      │
Save Model
      │
Predict
```

------------------------------------------------------------------------

# 5. Data Loading

``` python
import tensorflow as tf

train_ds = tf.keras.utils.image_dataset_from_directory(
    "dataset/train",
    image_size=(224,224),
    batch_size=32
)
```

------------------------------------------------------------------------

# 6. Data Preprocessing

Normalize pixel values:

``` python
normalization = tf.keras.layers.Rescaling(1./255)
```

Apply to every image before training.

------------------------------------------------------------------------

# 7. Image Augmentation

``` python
augmentation = tf.keras.Sequential([
    tf.keras.layers.RandomFlip("horizontal"),
    tf.keras.layers.RandomRotation(0.1),
    tf.keras.layers.RandomZoom(0.2)
])
```

------------------------------------------------------------------------

# 8. CNN Model

``` python
from tensorflow.keras import Sequential
from tensorflow.keras.layers import *

model = Sequential([
    Input(shape=(224,224,3)),
    Rescaling(1./255),

    Conv2D(32,3,activation="relu"),
    MaxPooling2D(),

    Conv2D(64,3,activation="relu"),
    MaxPooling2D(),

    Conv2D(128,3,activation="relu"),
    MaxPooling2D(),

    Flatten(),
    Dense(128,activation="relu"),
    Dropout(0.5),
    Dense(10,activation="softmax")
])
```

------------------------------------------------------------------------

# 9. Training

``` python
model.compile(
    optimizer="adam",
    loss="categorical_crossentropy",
    metrics=["accuracy"]
)

history = model.fit(
    train_ds,
    validation_data=val_ds,
    epochs=20
)
```

Recommended callbacks:

-   EarlyStopping
-   ModelCheckpoint
-   ReduceLROnPlateau

------------------------------------------------------------------------

# 10. Evaluation

Evaluate using:

``` python
model.evaluate(test_ds)
```

Useful metrics:

-   Accuracy
-   Precision
-   Recall
-   F1 Score
-   Confusion Matrix

Plot:

``` text
Training Accuracy

Validation Accuracy

Training Loss

Validation Loss
```

------------------------------------------------------------------------

# 11. Prediction

``` python
img = tf.keras.utils.load_img(
    "sample.jpg",
    target_size=(224,224)
)

x = tf.keras.utils.img_to_array(img)
x = tf.expand_dims(x,0)

prediction = model.predict(x)
```

Choose the class with the highest probability.

------------------------------------------------------------------------

# 12. Saving & Loading

Save:

``` python
model.save("cnn_classifier.keras")
```

Load:

``` python
from tensorflow.keras.models import load_model

model = load_model("cnn_classifier.keras")
```

------------------------------------------------------------------------

# 13. Best Practices

-   Use balanced datasets.
-   Normalize images.
-   Apply augmentation only to training data.
-   Monitor validation loss.
-   Save the best model.
-   Use transfer learning for small datasets.

------------------------------------------------------------------------

# 14. Mini Extensions

Try:

-   Transfer Learning with ResNet50
-   MobileNetV2
-   EfficientNet
-   Grad-CAM visualization
-   Streamlit deployment

------------------------------------------------------------------------

# 15. Interview Questions

### Why normalize images?

To stabilize training and improve convergence.

### Why use Dropout?

To reduce overfitting.

### Which optimizer is commonly used?

Adam.

### What is the purpose of validation data?

To tune the model without using the test set.

------------------------------------------------------------------------

# 16. Summary

You built a complete CNN image classification pipeline including:

-   Data loading
-   Preprocessing
-   Augmentation
-   CNN design
-   Training
-   Evaluation
-   Prediction
-   Model persistence

------------------------------------------------------------------------

# 17. What's Next?

**Lesson 143A -- Comparative Study of CNNs**

You'll revise the entire CNN chapter through comparison tables,
architecture timelines, decision trees, interview cheat sheets, and
real-world model selection guidelines.
