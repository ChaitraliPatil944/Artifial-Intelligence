# Chapter 11 -- Recurrent Neural Networks (RNNs)

# Lesson 155 -- Time Series Forecasting with RNNs

> **Time Series Forecasting is the task of predicting future values
> using historical sequential data. Recurrent Neural Networks (RNNs),
> LSTMs, and GRUs are well suited for this because they can model
> temporal dependencies and patterns over time.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand time series data.
-   Learn its major components.
-   Prepare sequential data for forecasting.
-   Compare one-step and multi-step forecasting.
-   Use RNNs, LSTMs, and GRUs for prediction.
-   Evaluate forecasting models.

------------------------------------------------------------------------

# Table of Contents

1.  What is Time Series?
2.  Components of Time Series
3.  Preparing Sequential Data
4.  Sliding Windows
5.  One-Step vs Multi-Step Forecasting
6.  Univariate vs Multivariate
7.  RNN/LSTM/GRU for Forecasting
8.  Evaluation Metrics
9.  Common Pitfalls
10. TensorFlow Example
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is Time Series?

A time series is a sequence of observations collected over time.

``` text
Day1 → Day2 → Day3 → Day4
```

Examples:

-   Stock prices
-   Weather
-   Electricity demand
-   Heart-rate monitoring
-   Website traffic

------------------------------------------------------------------------

# 2. Components of Time Series

### Trend

Long-term upward or downward movement.

``` text
📈 Increasing Sales
```

### Seasonality

Patterns repeating at fixed intervals.

``` text
Summer → Winter → Summer
```

### Cyclic Pattern

Long-term economic or business cycles with irregular duration.

### Noise

Random fluctuations that do not follow a predictable pattern.

------------------------------------------------------------------------

# 3. Preparing Sequential Data

Typical pipeline:

``` text
Raw Data
   │
Cleaning
   │
Normalization
   │
Window Creation
   │
Train / Validation / Test
```

Normalize values before training for stable optimization.

------------------------------------------------------------------------

# 4. Sliding Windows

Instead of feeding the entire sequence, use a fixed-size window.

Example:

``` text
Window Size = 3

[10, 12, 15] → 18

[12, 15, 18] → 20
```

This converts a long sequence into many training samples.

------------------------------------------------------------------------

# 5. One-Step vs Multi-Step Forecasting

  One-Step                   Multi-Step
  -------------------------- -------------------------------
  Predict next value         Predict several future values
  Easier                     More difficult
  Lower error accumulation   Errors may compound

------------------------------------------------------------------------

# 6. Univariate vs Multivariate

  Univariate             Multivariate
  ---------------------- -------------------------------
  One feature            Multiple features
  Example: temperature   Temperature + humidity + wind

------------------------------------------------------------------------

# 7. RNN/LSTM/GRU for Forecasting

  Model       Best Use
  ----------- ---------------------------------------
  SimpleRNN   Short sequences
  LSTM        Long-term dependencies
  GRU         Faster training with fewer parameters

Workflow:

``` text
Historical Data
      │
Sequence Windows
      │
LSTM / GRU
      │
Future Prediction
```

------------------------------------------------------------------------

# 8. Evaluation Metrics

### MAE

Average absolute error.

### MSE

Average squared error.

### RMSE

Square root of MSE.

### MAPE

Percentage prediction error.

Lower values generally indicate better forecasting performance.

------------------------------------------------------------------------

# 9. Common Pitfalls

-   Data leakage
-   Poor normalization
-   Too small window size
-   Ignoring seasonality
-   Overfitting
-   Predicting too far into the future without enough context

------------------------------------------------------------------------

# 10. TensorFlow Example

``` python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import LSTM, Dense

model = Sequential([
    LSTM(64, input_shape=(30,1)),
    Dense(1)
])

model.compile(
    optimizer="adam",
    loss="mse",
    metrics=["mae"]
)
```

------------------------------------------------------------------------

# 11. Mini Project

1.  Download a stock-price or weather dataset.
2.  Normalize the data.
3.  Create sliding windows.
4.  Train an LSTM.
5.  Evaluate using MAE and RMSE.
6.  Plot actual vs predicted values.

------------------------------------------------------------------------

# 12. Interview Questions

### What is time series forecasting?

Predicting future values from historical sequential observations.

### Why are LSTMs preferred?

They capture long-term dependencies better than basic RNNs.

### What is a sliding window?

A fixed-size sequence used to create supervised learning samples.

### Difference between univariate and multivariate forecasting?

Univariate uses one variable, while multivariate uses several related
variables.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   Time series fundamentals.
-   Trend, seasonality, cycles and noise.
-   Sliding windows.
-   One-step vs multi-step forecasting.
-   Univariate vs multivariate prediction.
-   Evaluation metrics.
-   TensorFlow implementation.

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 156 -- NLP Applications of RNNs**

You'll learn how RNNs, LSTMs, and GRUs are applied to natural language
processing tasks such as sentiment analysis, language modeling, text
generation, machine translation, named entity recognition, and speech
processing.
