# Chapter 4 – Python for AI

# Lesson 51 – Python Refresher

> **Before teaching an AI to learn, we must first learn to speak its language.**

## Learning Objectives

- Understand why Python became the language of AI.
- Learn Python's history.
- Explain why Python dominates AI.
- Review variables, data types, loops, functions, modules, and packages.
- Prepare for future AI libraries like NumPy and Pandas.

---

## Why Python?

Python is simple, readable, and has the richest ecosystem for AI development.

Example:

```python
if age >= 18:
    print("Eligible")
```

---

## History

- Created by Guido van Rossum (1989)
- Released in 1991
- Named after Monty Python's Flying Circus
- Python 3 is the modern industry standard

---

## Why Python for AI?

- NumPy
- Pandas
- Matplotlib
- Scikit-Learn
- TensorFlow
- PyTorch
- OpenCV

These libraries make AI development fast and practical.

---

## Variables

```python
name = "Alice"
age = 21
```

---

## Data Types

| Type | Example |
|------|---------|
| int | 10 |
| float | 3.14 |
| str | "AI" |
| bool | True |
| list | [1,2,3] |
| tuple | (1,2,3) |
| dict | {"a":1} |
| set | {1,2,3} |

---

## Conditions

```python
if age >= 18:
    print("Adult")
else:
    print("Minor")
```

---

## Loops

```python
for i in range(5):
    print(i)
```

```python
count = 0
while count < 5:
    print(count)
    count += 1
```

---

## Functions

```python
def square(x):
    return x * x
```

---

## Modules

```python
import math
print(math.sqrt(25))
```

---

## Virtual Environment

```bash
python -m venv myenv
```

Activate (Windows):

```bash
myenv\Scripts\activate
```

---

## Mini Project

Build a Student Grade Calculator that accepts marks, calculates average, and prints grades.

---

## Interview Questions

1. Why is Python preferred for AI?
2. Difference between List and Tuple?
3. What is indentation?
4. Difference between == and is?

---

## Summary

Python is the backbone of modern AI because of its simplicity, readability, and extensive ecosystem.

---

## Next Lesson

**Lesson 52 – NumPy**
