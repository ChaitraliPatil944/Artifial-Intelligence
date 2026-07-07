# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 157 -- RNN Project: Sentiment Analysis

> **In this capstone project, you'll build a complete sentiment analysis
> system using TensorFlow/Keras. The project combines text
> preprocessing, tokenization, embeddings, LSTMs, training, evaluation,
> and prediction into an industry-style NLP workflow.**

------------------------------------------------------------------------

# Learning Objectives

-   Build an end-to-end NLP project.
-   Apply text preprocessing.
-   Train an LSTM classifier.
-   Evaluate model performance.
-   Save and reload trained models.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  Problem Statement
2.  Dataset
3.  Project Structure
4.  Workflow
5.  Text Preprocessing
6.  Tokenization & Padding
7.  LSTM Model
8.  Training
9.  Evaluation
10. Prediction
11. Saving & Loading
12. Best Practices
13. Mini Extensions
14. Interview Questions
15. Summary
16. What's Next?

------------------------------------------------------------------------

# 1. Problem Statement

Build an AI model that classifies movie reviews as:

-   Positive 😊
-   Negative ☹️

------------------------------------------------------------------------

# 2. Dataset

Recommended dataset:

-   IMDb Movie Reviews

Typical split:

``` text
Train      70%

Validation 15%

Test       15%
```

------------------------------------------------------------------------

# 3. Project Structure

``` text
sentiment-analysis/
│
├── dataset/
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
Raw Reviews
     │
Cleaning
     │
Tokenization
     │
Padding
     │
Embeddings
     │
LSTM
     │
Prediction
```

------------------------------------------------------------------------

# 5. Text Preprocessing

Common preprocessing:

-   Lowercasing
-   Remove HTML tags
-   Remove punctuation
-   Tokenization
-   Padding

Example:

``` text
"I absolutely loved this movie!"

↓

["i","absolutely","loved","this","movie"]
```

------------------------------------------------------------------------

# 6. Tokenization & Padding

``` python
from tensorflow.keras.preprocessing.text import Tokenizer
from tensorflow.keras.preprocessing.sequence import pad_sequences

tokenizer = Tokenizer(num_words=10000)
tokenizer.fit_on_texts(train_texts)

seq = tokenizer.texts_to_sequences(train_texts)
seq = pad_sequences(seq, maxlen=200)
```

------------------------------------------------------------------------

# 7. LSTM Model

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Embedding, LSTM, Dense, Dropout

model = Sequential([
    Embedding(10000,128,input_length=200),
    LSTM(128),
    Dropout(0.5),
    Dense(1,activation="sigmoid")
])
```

Compile:

``` python
model.compile(
    optimizer="adam",
    loss="binary_crossentropy",
    metrics=["accuracy"]
)
```

------------------------------------------------------------------------

# 8. Training

``` python
history = model.fit(
    X_train,
    y_train,
    validation_data=(X_val,y_val),
    epochs=10,
    batch_size=32
)
```

Recommended callbacks:

-   EarlyStopping
-   ModelCheckpoint

------------------------------------------------------------------------

# 9. Evaluation

Evaluate using:

``` python
model.evaluate(X_test,y_test)
```

Metrics:

-   Accuracy
-   Precision
-   Recall
-   F1 Score
-   Confusion Matrix

Plot:

-   Training Accuracy
-   Validation Accuracy
-   Training Loss
-   Validation Loss

------------------------------------------------------------------------

# 10. Prediction

``` python
review = ["This movie was amazing!"]

seq = tokenizer.texts_to_sequences(review)
seq = pad_sequences(seq,maxlen=200)

prediction = model.predict(seq)
```

If prediction \> 0.5:

``` text
Positive Review
```

Else:

``` text
Negative Review
```

------------------------------------------------------------------------

# 11. Saving & Loading

``` python
model.save("sentiment_lstm.keras")
```

Load later:

``` python
from tensorflow.keras.models import load_model

model = load_model("sentiment_lstm.keras")
```

------------------------------------------------------------------------

# 12. Best Practices

-   Use balanced datasets.
-   Limit vocabulary size.
-   Pad sequences consistently.
-   Prevent overfitting with dropout.
-   Save the best model.
-   Tune sequence length.

------------------------------------------------------------------------

# 13. Mini Extensions

Try:

-   Bidirectional LSTM
-   GRU
-   Attention layer
-   Transformer encoder
-   Deploy with Streamlit

------------------------------------------------------------------------

# 14. Interview Questions

### Why use an Embedding layer?

To learn dense vector representations of words.

### Why LSTM instead of SimpleRNN?

LSTM handles long-term dependencies better.

### Why pad sequences?

Neural networks require inputs of consistent length.

### Which activation is used for binary sentiment analysis?

Sigmoid.

------------------------------------------------------------------------

# 15. Summary

You built a complete sentiment analysis pipeline including:

-   Text preprocessing
-   Tokenization
-   Padding
-   Embeddings
-   LSTM model
-   Training
-   Evaluation
-   Prediction
-   Model persistence

------------------------------------------------------------------------

# 16. What's Next?

**Lesson 157A -- Comparative Study of RNNs**

You'll revise the entire RNN chapter through comparison tables,
architecture diagrams, interview cheat sheets, decision trees, and
real-world model selection guidelines.
