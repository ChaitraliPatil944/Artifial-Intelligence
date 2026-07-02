# Machine Learning - Lesson 1: Data

> **Goal:** Understand what data is, why it is essential for Machine
> Learning, where it comes from, and how it is used in industry.

------------------------------------------------------------------------

# 1. Why Do We Need Data?

Imagine teaching a child what a dog is.

``` text
🐶 Dog
🐶 Dog
🐶 Dog
🐶 Dog
```

After seeing many examples, the child learns to recognize dogs.

Machine Learning works similarly.

Without examples, a computer cannot learn.

Those examples are called **Data**.

------------------------------------------------------------------------

# 2. Definition

**Data** is a collection of facts, observations, measurements, or
information that can be processed to discover patterns and make
predictions.

Examples:

-   Age = 25
-   Salary = ₹50,000
-   Image of a cat
-   Voice recording
-   GPS location
-   Bank transaction

Everything above is data.

------------------------------------------------------------------------

# 3. Why Is Data Important?

Machine Learning learns from data.

``` text
Data
  │
  ▼
Machine Learning Model
  │
  ▼
Learns Patterns
  │
  ▼
Makes Predictions
```

Without data, the model cannot learn.

------------------------------------------------------------------------

# 4. Why Is Data Called the Fuel of AI?

Car analogy:

``` text
Car
 │
 ▼
Fuel
 │
 ▼
Runs
```

AI analogy:

``` text
Machine Learning Model
        │
        ▼
       Data
        │
        ▼
     Learns
```

Algorithms are the chef.

Data is the ingredients.

A great chef cannot cook without ingredients.

------------------------------------------------------------------------

# 5. Data Is Everywhere

Examples:

## Smartphone

-   Photos
-   Videos
-   Messages
-   GPS
-   Battery usage

## Bank

-   Transactions
-   Account balance
-   Payment history

## Netflix

-   Watch history
-   Ratings
-   Search history

## Amazon

-   Products viewed
-   Purchases
-   Cart history

## Smartwatch

-   Heart rate
-   Sleep
-   Steps

------------------------------------------------------------------------

# 6. Sources of Data

``` text
                     DATA
                       │
      ┌────────────────┼────────────────┐
      │                │                │
   Humans          Machines          Nature
      │                │                │
 Forms            Sensors          Weather
 Photos           Cameras          Rainfall
 Reviews          GPS              Temperature
 Emails           IoT Devices      Wind Speed
```

------------------------------------------------------------------------

# 7. Types of Data

``` text
                Data
                  │
      ┌───────────┼───────────┐
      │           │           │
 Structured   Semi-Structured  Unstructured
```

## Structured Data

Organized into rows and columns.

  Name      Age   Salary
  ------- ----- --------
  Alice      25    30000
  Bob        28    45000

Examples:

-   SQL databases
-   Excel sheets
-   Banking records

------------------------------------------------------------------------

## Semi-Structured Data

Example:

``` json
{
  "name": "Alice",
  "age": 25,
  "city": "Pune"
}
```

Examples:

-   JSON
-   XML
-   HTML

------------------------------------------------------------------------

## Unstructured Data

Examples:

-   Images
-   Videos
-   Audio
-   PDFs
-   Emails
-   Social media posts
-   Medical scans

Most of the world's data is unstructured.

------------------------------------------------------------------------

# 8. Raw Data vs Information

Raw data:

``` text
101
102
103
104
```

Meaningful information:

``` text
Student Roll Numbers
101
102
103
104
```

Context transforms raw data into useful information.

------------------------------------------------------------------------

# 9. Industry Examples

## Netflix

``` text
User Watches Movie
        │
        ▼
 Collect Data
        │
        ▼
 Machine Learning
        │
        ▼
Recommendations
```

## Banking

``` text
Transaction
     │
     ▼
Collect Data
     │
     ▼
Fraud Detection
```

## Healthcare

``` text
Medical Image
      │
      ▼
Machine Learning
      │
      ▼
Disease Detection
```

## Agriculture

``` text
Leaf Image
     │
     ▼
Machine Learning
     │
     ▼
Disease Detection
```

------------------------------------------------------------------------

# 10. Characteristics of Good Data

Good data should be:

-   Accurate
-   Complete
-   Relevant
-   Consistent
-   Up-to-date
-   Representative

------------------------------------------------------------------------

# 11. Garbage In, Garbage Out (GIGO)

``` text
Bad Data
   │
   ▼
Machine Learning
   │
   ▼
Bad Model
   │
   ▼
Wrong Predictions
```

Even the best algorithm cannot compensate for poor-quality data.

------------------------------------------------------------------------

# 12. Interview Questions

## Basic

**What is data?**

Data is a collection of facts or information that can be processed to
discover patterns and support decision-making.

### Intermediate

**Why is data important in Machine Learning?**

Machine Learning learns patterns from data. Without data, a model cannot
learn or make useful predictions.

### Advanced

**Is improving the algorithm always better than improving the data?**

No. In many real-world applications, improving data quality has a
greater impact than changing the algorithm.

------------------------------------------------------------------------

# 13. Common Mistakes

❌ Starting with algorithms instead of understanding data.

✅ Begin with understanding and collecting quality data.

❌ Assuming more data is always better.

✅ High-quality, relevant data is usually more valuable than large
amounts of poor-quality data.

------------------------------------------------------------------------

# 14. Memory Map

``` text
                          DATA
                            │
        ┌───────────────────┼───────────────────┐
        │                   │                   │
 Facts & Information   Sources of Data     Powers AI
        │                   │                   │
 Images, Audio, Text   Humans, Sensors,    Machine Learning
 Videos, Tables        Nature, Devices     Learns Patterns
                            │
          ┌─────────────────┼─────────────────┐
          │                 │                 │
     Structured      Semi-Structured    Unstructured
```

------------------------------------------------------------------------

# Lesson Summary

-   Data is the foundation of Machine Learning.
-   AI systems learn from examples.
-   Data can be structured, semi-structured, or unstructured.
-   High-quality data is often more important than a more complex
    algorithm.
-   Remember the principle: **Garbage In, Garbage Out (GIGO).**

------------------------------------------------------------------------

# Next Lesson

``` text
Data
 │
 ▼
Dataset
 │
 ▼
Sample
 │
 ▼
Feature
 │
 ▼
Label
 │
 ▼
Model
```
