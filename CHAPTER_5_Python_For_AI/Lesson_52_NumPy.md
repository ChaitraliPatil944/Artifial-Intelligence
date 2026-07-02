# Chapter 4 – Python for AI

# Lesson 52 – NumPy

> **NumPy is the mathematical engine behind modern Artificial Intelligence.**

---

# Learning Objectives

By the end of this lesson you will:

- Understand why NumPy was created.
- Learn why Python lists are insufficient for AI.
- Understand arrays and vectorization.
- Perform mathematical operations efficiently.
- Learn broadcasting and array indexing.
- Prepare for interview questions involving NumPy.

---

# Table of Contents

1. What is NumPy?
2. Why NumPy was Invented
3. Python Lists vs NumPy Arrays
4. Installing NumPy
5. Creating Arrays
6. Array Dimensions
7. Data Types
8. Indexing & Slicing
9. Reshaping Arrays
10. Mathematical Operations
11. Vectorization
12. Broadcasting
13. Random Module
14. Real-World AI Usage
15. Mini Project
16. Interview Questions
17. Summary
18. What's Next?

---

# 1. What is NumPy?

**NumPy (Numerical Python)** is a high-performance Python library used for numerical computing.

It provides a powerful object called the **ndarray (N-dimensional Array)**, which is much faster and more memory-efficient than Python lists.

---

# 2. Why NumPy was Invented

Python lists are flexible but slow for mathematical computations.

AI models work with millions of numbers.

Instead of looping through each value manually, NumPy performs operations on entire arrays simultaneously.

---

# 3. Python Lists vs NumPy Arrays

Python List

```python
numbers = [1,2,3,4]
```

NumPy Array

```python
import numpy as np

numbers = np.array([1,2,3,4])
```

Advantages of NumPy:

- Faster
- Less memory
- Optimized C backend
- Supports vectorized operations

---

# 4. Installing NumPy

```bash
pip install numpy
```

Import

```python
import numpy as np
```

---

# 5. Creating Arrays

```python
import numpy as np

a = np.array([1,2,3])

b = np.zeros((2,3))

c = np.ones((3,3))

d = np.arange(1,11)

e = np.linspace(0,1,5)
```

---

# 6. Array Dimensions

```python
a = np.array([1,2,3])

b = np.array([[1,2],[3,4]])
```

1D

```
[1 2 3]
```

2D

```
1 2
3 4
```

3D arrays are commonly used in image processing.

---

# 7. Data Types

```python
arr = np.array([1,2,3], dtype=np.float32)
```

Common types:

- int32
- int64
- float32
- float64
- bool

---

# 8. Indexing & Slicing

```python
arr = np.array([10,20,30,40,50])

print(arr[0])
print(arr[-1])
print(arr[1:4])
```

Output

```
10
50
[20 30 40]
```

---

# 9. Reshaping Arrays

```python
arr = np.arange(12)

matrix = arr.reshape(3,4)
```

ASCII

```
0 1 2 3
4 5 6 7
8 9 10 11
```

---

# 10. Mathematical Operations

```python
a = np.array([1,2,3])
b = np.array([4,5,6])

print(a+b)
print(a*b)
print(a**2)
```

Output

```
[5 7 9]
[4 10 18]
[1 4 9]
```

---

# 11. Vectorization

Instead of writing loops:

```python
result = arr * 2
```

NumPy applies the operation to every element internally.

This is called **vectorization**.

---

# 12. Broadcasting

```python
arr = np.array([[1,2],[3,4]])

print(arr + 10)
```

Output

```
11 12
13 14
```

Broadcasting automatically expands compatible dimensions.

---

# 13. Random Module

```python
np.random.rand(3)

np.random.randint(1,10,size=5)

np.random.seed(42)
```

Used extensively in machine learning for initializing weights and creating datasets.

---

# 14. Real-World AI Usage

NumPy is used for:

- Image data
- Feature matrices
- Neural network inputs
- Statistical calculations
- Scientific computing

Almost every AI framework internally depends on NumPy concepts.

---

# 15. Mini Project

Create a program that:

- Generates marks for 100 students using NumPy.
- Calculates mean, median, maximum and minimum.
- Displays students scoring above average.

---

# 16. Interview Questions

### Why is NumPy faster than Python lists?

Because NumPy stores homogeneous data in contiguous memory and executes operations using optimized C code.

### What is vectorization?

Performing operations on an entire array without explicit Python loops.

### What is broadcasting?

Automatically expanding arrays of compatible shapes during operations.

### Difference between list and ndarray?

Lists store heterogeneous objects.
NumPy arrays store homogeneous values efficiently.

---

# 17. Summary

In this lesson you learned:

- Why NumPy exists
- Arrays
- Vectorization
- Broadcasting
- Indexing
- Reshaping
- Mathematical operations
- AI applications

---

# 18. What's Next?

**Lesson 53 – Pandas**

You'll learn how AI engineers load, clean, analyze and manipulate datasets before training machine learning models.
