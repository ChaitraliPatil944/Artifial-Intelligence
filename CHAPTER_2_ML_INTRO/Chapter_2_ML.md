# Chapter 2: Machine Learning (Part 1)

> Goal: Understand why Machine Learning was invented, how it differs
> from traditional programming, and how it fits into Artificial
> Intelligence.

------------------------------------------------------------------------

# 1. Why Was Machine Learning Invented?

Imagine you own a mango farm with **10,000 mangoes**.

You want a computer to identify whether a mango is ripe.

You try writing rules.

``` text
IF Color == Yellow
THEN Ripe
```

Problem: - Some ripe mangoes are green. - Some unripe mangoes are
yellow.

Eventually you realize that writing rules for every situation is
impossible.

------------------------------------------------------------------------

# 2. Traditional Programming

``` text
Programmer
    │
Writes Rules
    │
    ▼
Computer
    │
    ▼
Answer
```

This works well when rules are obvious.

It fails for: - Face Recognition - Spam Detection - Language
Translation - Self Driving Cars - Disease Detection

------------------------------------------------------------------------

# 3. The Revolutionary Idea

Instead of writing every rule manually...

**Can the computer discover the rules from data?**

That idea became **Machine Learning**.

------------------------------------------------------------------------

# 4. Traditional Programming vs Machine Learning

## Traditional Programming

``` text
Rules + Data
      │
      ▼
 Computer
      │
      ▼
 Prediction
```

## Machine Learning

``` text
Data + Correct Answers
          │
          ▼
Learning Algorithm
          │
          ▼
Learns Rules (Model)
          │
          ▼
Future Predictions
```

The learned rules are called a **Model**.

------------------------------------------------------------------------

# 5. Child Analogy

Instead of telling a child every rule for identifying a dog, show
thousands of dog pictures.

The child discovers patterns.

Machine Learning works in a similar way using mathematics and data.

------------------------------------------------------------------------

# 6. Definition

> Machine Learning is a branch of Artificial Intelligence that enables
> computers to learn patterns from data and improve their performance
> without being explicitly programmed for every situation.

------------------------------------------------------------------------

# 7. AI vs Machine Learning

``` text
Artificial Intelligence
        │
        ▼
Machine Learning
        │
        ▼
Deep Learning
```

------------------------------------------------------------------------

# 8. Learning Patterns

  Hours Studied   Passed?
  --------------- ---------
  1               No
  2               No
  3               No
  4               Yes
  5               Yes
  6               Yes

The computer discovers the relationship from examples.

------------------------------------------------------------------------

# 9. Does Machine Learning Really Learn?

Machine Learning does not think.

It learns mathematical relationships from data.

``` text
Image
  │
  ▼
Find Patterns
  │
  ▼
Prediction
```

------------------------------------------------------------------------

# 10. History

-   1943: McCulloch & Pitts proposed the first artificial neuron.
-   1950: Alan Turing proposed the Turing Test.
-   1952: Arthur Samuel popularized the term Machine Learning.
-   1957: Frank Rosenblatt introduced the Perceptron.
-   1980s: Better neural network learning methods.
-   1990s: Faster computers and more data accelerated ML.
-   2010s: GPUs led to Deep Learning.

------------------------------------------------------------------------

# 11. Evolution

``` text
Rule-Based AI
      │
      ▼
Machine Learning
      │
      ▼
Deep Learning
      │
      ▼
Transformers
      │
      ▼
Large Language Models
      │
      ▼
Generative AI
```

------------------------------------------------------------------------

# 12. Most Important Diagram

``` text
Traditional Programming

Rules + Data
      │
      ▼
 Computer
      │
      ▼
 Prediction


Machine Learning

Data + Correct Answers
          │
          ▼
Learning Algorithm
          │
          ▼
 Learned Model
          │
          ▼
Future Predictions
```

Remember:

**The programmer no longer writes the rules. The model learns them from
data.**

------------------------------------------------------------------------

# 13. Quick Revision

-   AI is the broad field.
-   Machine Learning is a subset of AI.
-   ML learns patterns from examples.
-   Training produces a model.
-   Models make predictions.

------------------------------------------------------------------------

# 14. Interview Questions

## Basic

**What is Machine Learning?**

Machine Learning is a branch of AI that enables computers to learn from
data and make predictions without being explicitly programmed for every
situation.

## Intermediate

**Why was Machine Learning invented?**

Because manually writing rules for complex real-world problems is
impractical.

## Advanced

**Why do we say Machine Learning learns?**

Because it adjusts mathematical parameters based on data to improve
predictions.

------------------------------------------------------------------------

# 15. Memory Map

``` text
                  Machine Learning
                          │
      ┌───────────────────┼───────────────────┐
      │                   │                   │
   Learns           Uses Data          Makes Predictions
```

------------------------------------------------------------------------

# Next Chapter

``` text
Raw Data
    │
    ▼
Dataset
    │
    ▼
Features
    │
    ▼
Labels
    │
    ▼
Training Data
    │
    ▼
Model
    │
    ▼
Prediction
```
