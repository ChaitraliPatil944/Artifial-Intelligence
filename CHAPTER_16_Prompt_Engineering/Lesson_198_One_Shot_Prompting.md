# Chapter 16 -- Prompt Engineering

# Lesson 198 -- One-Shot Prompting

> **One-Shot Prompting is a prompting technique where a Large Language
> Model (LLM) is given exactly one example of the desired task before
> being asked to solve a new instance. The example acts as a
> demonstration, helping the model infer the expected pattern, style, or
> output format.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand One-Shot Prompting.
-   Learn why one example improves performance.
-   Design effective one-shot prompts.
-   Compare One-Shot with Zero-Shot.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is One-Shot Prompting?
2.  Why One-Shot Works
3.  Prompt Structure
4.  Examples
5.  Zero-Shot vs One-Shot
6.  Applications
7.  Best Practices
8.  Common Mistakes
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is One-Shot Prompting?

The model is shown **one demonstration** before solving the task.

``` text
Example
   │
New Input
   │
LLM
   │
Answer
```

Example:

``` text
Example:
Input: I love this movie.
Output: Positive

Now classify:
Input: The food was awful.
Output:
```

------------------------------------------------------------------------

# 2. Why One-Shot Works

The example teaches the model:

-   Expected format
-   Desired reasoning pattern
-   Output style
-   Task interpretation

Even a single example can significantly reduce ambiguity.

------------------------------------------------------------------------

# 3. Prompt Structure

``` text
Task Description
      │
One Example
      │
Actual Input
      │
Expected Output
```

------------------------------------------------------------------------

# 4. Examples

### Translation

``` text
Example

English: Hello
French: Bonjour

Translate:

English: Good Night
French:
```

### JSON Output

``` text
Example

Input:
Alice is 20.

Output:
{"name":"Alice","age":20}

Now process:

Bob is 35.
```

------------------------------------------------------------------------

# 5. Zero-Shot vs One-Shot

  Feature              Zero-Shot   One-Shot
  -------------------- ----------- -----------
  Examples Provided    ❌          ✅ One
  Easy Tasks           Excellent   Excellent
  Ambiguous Tasks      Moderate    Better
  Output Consistency   Lower       Higher

------------------------------------------------------------------------

# 6. Applications

-   Text classification
-   Translation
-   Information extraction
-   JSON generation
-   Code generation
-   Data formatting

------------------------------------------------------------------------

# 7. Best Practices

-   Use a high-quality example.
-   Match the desired output exactly.
-   Keep the example relevant.
-   Avoid overly complex demonstrations.

------------------------------------------------------------------------

# 8. Common Mistakes

-   Using a poor example
-   Mixing multiple tasks
-   Inconsistent formatting
-   Example unrelated to the real task

------------------------------------------------------------------------

# 9. Python Example

``` python
from openai import OpenAI

client = OpenAI()

prompt = """
Example:
Input: I love this movie.
Output: Positive

Now classify:

Input: The service was terrible.
Output:
"""

response = client.responses.create(
    model="gpt-4.1",
    input=prompt
)

print(response.output_text)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Create five one-shot prompts.
2.  Compare with zero-shot prompts.
3.  Measure output consistency.
4.  Test structured JSON generation.
5.  Document the improvements.

------------------------------------------------------------------------

# 11. Interview Questions

### What is One-Shot Prompting?

Providing exactly one example before the actual task.

### Why is it useful?

It demonstrates the expected pattern and output format.

### When should it be preferred?

For structured or slightly ambiguous tasks.

### Difference from Zero-Shot?

Zero-shot provides no examples, while one-shot provides one
demonstration.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   One-Shot Prompting
-   Why examples help
-   Prompt structure
-   Comparison with Zero-Shot
-   Applications
-   Python implementation

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 199 -- Few-Shot Prompting**

You'll learn how providing multiple demonstrations helps LLMs solve
complex tasks with greater accuracy, consistency, and robustness.
