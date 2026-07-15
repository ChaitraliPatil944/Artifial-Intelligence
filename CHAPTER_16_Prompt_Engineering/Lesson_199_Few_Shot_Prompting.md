# Chapter 16 -- Prompt Engineering

# Lesson 199 -- Few-Shot Prompting

> **Few-Shot Prompting is a prompting technique where a Large Language
> Model (LLM) is provided with a small number of examples before being
> asked to solve a new task. These demonstrations help the model infer
> the desired pattern, reasoning process, style, and output format
> without updating the model's parameters.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Few-Shot Prompting.
-   Learn why multiple examples improve performance.
-   Understand In-Context Learning (ICL).
-   Compare Zero-, One-, and Few-Shot prompting.
-   Design effective few-shot prompts.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Few-Shot Prompting?
2.  Why Few-Shot Works
3.  In-Context Learning
4.  Prompt Structure
5.  Examples
6.  Zero vs One vs Few Shot
7.  Applications
8.  Best Practices
9.  Common Mistakes
10. Python Example
11. Mini Project
12. Interview Questions
13. Summary
14. What's Next?

------------------------------------------------------------------------

# 1. What is Few-Shot Prompting?

Instead of giving only instructions or one example, we provide several
demonstrations.

``` text
Examples
    │
New Task
    │
LLM
    │
Prediction
```

Example:

``` text
Input: I love this book.
Output: Positive

Input: The food was terrible.
Output: Negative

Input: The movie was fantastic.
Output:
```

------------------------------------------------------------------------

# 2. Why Few-Shot Works

Each example teaches the model:

-   Desired format
-   Reasoning pattern
-   Label style
-   Domain-specific behavior

Multiple demonstrations reduce ambiguity.

------------------------------------------------------------------------

# 3. In-Context Learning (ICL)

Few-shot prompting is possible because modern LLMs perform **In-Context
Learning**.

``` text
Prompt
   │
Examples
   │
Pattern Recognition
   │
Apply Pattern
```

The model learns from the examples during inference without changing its
weights.

------------------------------------------------------------------------

# 4. Prompt Structure

``` text
Task Description
      │
Example 1
      │
Example 2
      │
Example 3
      │
New Input
      │
Output
```

------------------------------------------------------------------------

# 5. Examples

### Translation

``` text
English: Hello
French: Bonjour

English: Thank you
French: Merci

English: Good Night
French:
```

### JSON Extraction

``` text
Alice is 20.
{"name":"Alice","age":20}

Bob is 35.
{"name":"Bob","age":35}

Charlie is 28.
```

------------------------------------------------------------------------

# 6. Zero vs One vs Few Shot

  Feature         Zero-Shot   One-Shot   Few-Shot
  --------------- ----------- ---------- ------------
  Examples        0           1          Multiple
  Accuracy        Good        Better     Often Best
  Consistency     Moderate    High       Very High
  Complex Tasks   Limited     Better     Excellent

------------------------------------------------------------------------

# 7. Applications

-   Classification
-   Translation
-   Information extraction
-   Structured JSON generation
-   Code generation
-   Mathematical reasoning
-   Domain-specific NLP

------------------------------------------------------------------------

# 8. Best Practices

-   Use diverse examples.
-   Keep formatting consistent.
-   Cover edge cases.
-   Place the most relevant examples first.
-   Avoid contradictory demonstrations.

------------------------------------------------------------------------

# 9. Common Mistakes

-   Too many unnecessary examples
-   Inconsistent outputs
-   Mixing unrelated tasks
-   Poor-quality demonstrations

------------------------------------------------------------------------

# 10. Python Example

``` python
from openai import OpenAI

client = OpenAI()

prompt = """
Example 1:
Input: I love AI.
Output: Positive

Example 2:
Input: The weather is awful.
Output: Negative

Now classify:

Input: This phone is amazing.
Output:
"""

response = client.responses.create(
    model="gpt-4.1",
    input=prompt
)

print(response.output_text)
```

------------------------------------------------------------------------

# 11. Mini Project

1.  Build zero-shot, one-shot, and few-shot prompts.
2.  Test sentiment analysis.
3.  Test JSON extraction.
4.  Compare accuracy and consistency.
5.  Document your observations.

------------------------------------------------------------------------

# 12. Interview Questions

### What is Few-Shot Prompting?

Providing multiple demonstrations before asking the model to solve a new
task.

### What is In-Context Learning?

The model recognizes patterns from examples within the prompt without
updating its parameters.

### Why is Few-Shot better than Zero-Shot?

Examples reduce ambiguity and improve consistency.

### Can too many examples be harmful?

Yes. They increase token usage and may introduce noise or exceed context
limits.

------------------------------------------------------------------------

# 13. Summary

You learned:

-   Few-Shot Prompting
-   In-Context Learning
-   Prompt structure
-   Best practices
-   Applications
-   Python implementation

------------------------------------------------------------------------

# 14. What's Next?

**Lesson 200 -- Chain of Thought (CoT) Prompting**

You'll learn how prompting models to reason through intermediate steps
improves performance on complex mathematical, logical, and multi-step
reasoning tasks.
