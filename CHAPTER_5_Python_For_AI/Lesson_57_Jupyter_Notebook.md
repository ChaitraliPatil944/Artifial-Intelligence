# Chapter 4 – Python for AI

# Lesson 57 – Jupyter Notebook

> **Jupyter Notebook is where ideas become experiments. It allows AI engineers to write code, explain concepts, visualize results, and document everything in one place.**

---

# Learning Objectives

By the end of this lesson, you will:

- Understand what Jupyter Notebook is.
- Learn why it became the standard tool for Data Science and AI.
- Work with notebooks, cells, and kernels.
- Use Markdown and code together.
- Learn common magic commands.
- Follow best practices for AI projects.
- Prepare for interview questions.

---

# Table of Contents

1. What is Jupyter Notebook?
2. History of Project Jupyter
3. Why Jupyter was Created
4. Installing Jupyter
5. Notebook Structure
6. Code Cells
7. Markdown Cells
8. Running Cells
9. The Kernel
10. Magic Commands
11. Keyboard Shortcuts
12. Exporting Notebooks
13. AI Workflow with Jupyter
14. Best Practices
15. Mini Project
16. Interview Questions
17. Summary
18. What's Next?

---

# 1. What is Jupyter Notebook?

Jupyter Notebook is an interactive development environment where code, text, equations, images and charts can exist in a single document.

It is widely used for:

- Data Science
- Machine Learning
- Deep Learning
- Research
- Education

---

# 2. History of Project Jupyter

Jupyter evolved from the IPython Notebook project.

The name **Jupyter** comes from:

- **Ju** → Julia
- **Py** → Python
- **R** → R Programming Language

Today it supports dozens of programming languages.

---

# 3. Why Jupyter was Created

Traditional programming requires editing a file and running the whole program.

Jupyter allows experimentation one step at a time.

```
Write Code
    │
    ▼
Run Cell
    │
    ▼
See Output
    │
    ▼
Modify
    │
    ▼
Run Again
```

This rapid feedback makes research much easier.

---

# 4. Installing Jupyter

```bash
pip install notebook
```

Launch:

```bash
jupyter notebook
```

Or install JupyterLab:

```bash
pip install jupyterlab
```

---

# 5. Notebook Structure

A notebook contains **cells**.

```
Notebook
│
├── Markdown Cell
├── Code Cell
├── Markdown Cell
└── Code Cell
```

Each cell can be executed independently.

---

# 6. Code Cells

Example:

```python
x = 10
y = 20

print(x + y)
```

Output appears immediately below the cell.

---

# 7. Markdown Cells

Markdown is used for documentation.

Example:

```markdown
# Machine Learning

This notebook explains Linear Regression.
```

Use Markdown to keep notebooks readable and well organized.

---

# 8. Running Cells

Ways to execute:

- Shift + Enter → Run and move next
- Ctrl + Enter → Run current cell
- Alt + Enter → Run and create new cell

---

# 9. The Kernel

The kernel executes notebook code.

```
Notebook
    │
    ▼
Kernel
    │
    ▼
Python Interpreter
    │
    ▼
Output
```

If the kernel stops, code execution also stops.

Restart the kernel when variables become inconsistent.

---

# 10. Magic Commands

Useful commands:

```python
%timeit
```

Measures execution time.

```python
%pwd
```

Shows current directory.

```python
%who
```

Lists existing variables.

```python
%%time
```

Measures execution time for an entire cell.

---

# 11. Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| A | Insert cell above |
| B | Insert cell below |
| DD | Delete cell |
| M | Convert to Markdown |
| Y | Convert to Code |
| Shift + Enter | Run cell |

---

# 12. Exporting Notebooks

Export formats:

- HTML
- PDF
- Markdown
- Python (.py)

Menu:

```
File
   │
   ▼
Download As
```

---

# 13. AI Workflow with Jupyter

```
Load Dataset
      │
      ▼
Explore Data
      │
      ▼
Visualize
      │
      ▼
Train Model
      │
      ▼
Evaluate
      │
      ▼
Document Results
```

Researchers often publish notebooks alongside their work for reproducibility.

---

# 14. Best Practices

- Give notebooks meaningful names.
- Keep code cells short.
- Use Markdown to explain every major step.
- Restart the kernel before final execution.
- Remove unused cells.
- Save frequently.

---

# 15. Mini Project

Create a notebook that:

1. Loads a CSV dataset.
2. Displays the first five rows.
3. Creates a visualization.
4. Calculates summary statistics.
5. Writes observations using Markdown.

---

# 16. Interview Questions

### What is Jupyter Notebook?

An interactive environment for writing, executing and documenting code.

### Why is Jupyter popular in AI?

Because it supports experimentation, visualization and documentation in one place.

### What is a kernel?

The process responsible for executing notebook code.

### Difference between Code and Markdown cells?

- Code cells execute programs.
- Markdown cells provide documentation.

---

# 17. Summary

You learned:

- What Jupyter Notebook is.
- Why it became popular.
- Notebook structure.
- Kernels.
- Markdown and code cells.
- Magic commands.
- AI workflow.

---

# 18. What's Next?

**Lesson 58 – Scikit-Learn**

You'll learn the most widely used Machine Learning library for building, training and evaluating classical ML models.
