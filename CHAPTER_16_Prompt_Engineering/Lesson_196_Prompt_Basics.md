# Chapter 16 -- Prompt Engineering

# Lesson 196 -- Prompt Basics

> **Prompt Engineering is the practice of designing, structuring, and
> optimizing inputs (prompts) given to Large Language Models (LLMs) to
> obtain accurate, reliable, and useful outputs.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Prompt Engineering.
-   Learn why prompts matter.
-   Study the anatomy of a good prompt.
-   Learn prompting best practices.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Prompt Engineering?
2.  Why Prompt Engineering Matters
3.  How LLMs Read Prompts
4.  Anatomy of a Good Prompt
5.  Types of Prompts
6.  Prompt Workflow
7.  Best Practices
8.  Common Mistakes
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is Prompt Engineering?

A prompt is the instruction given to an LLM.

``` text
User Prompt
     │
Large Language Model
     │
Generated Response
```

Prompt Engineering improves those instructions to obtain more accurate,
useful, and consistent outputs.

------------------------------------------------------------------------

# 2. Why Prompt Engineering Matters

A vague prompt often produces vague answers.

Poor prompt:

``` text
Explain Python.
```

Improved prompt:

``` text
Explain Python to a beginner.

Include:
- Variables
- Loops
- Functions

Use simple language.

Maximum 300 words.

Return bullet points.
```

------------------------------------------------------------------------

# 3. How LLMs Read Prompts

``` text
Prompt
   │
Tokenization
   │
Embeddings
   │
Transformer
   │
Next Token Prediction
```

The model relies on:

-   Context
-   Instructions
-   Previous conversation
-   Learned knowledge

------------------------------------------------------------------------

# 4. Anatomy of a Good Prompt

A strong prompt usually contains:

``` text
Goal
 │
Context
 │
Constraints
 │
Output Format
```

Example:

``` text
Task:
Summarize this report.

Audience:
College students.

Length:
200 words.

Output:
Bullet points.
```

------------------------------------------------------------------------

# 5. Types of Prompts

-   Information prompts
-   Creative prompts
-   Coding prompts
-   Translation prompts
-   Summarization prompts
-   Reasoning prompts
-   Data analysis prompts

------------------------------------------------------------------------

# 6. Prompt Workflow

``` text
Define Goal
      │
Provide Context
      │
Specify Constraints
      │
Specify Output Format
      │
Review
      │
Refine
```

------------------------------------------------------------------------

# 7. Best Practices

-   Be specific.
-   Give context.
-   Mention the audience.
-   Specify the desired format.
-   Add constraints when necessary.
-   Iterate and improve.

------------------------------------------------------------------------

# 8. Common Mistakes

Avoid:

-   Ambiguous instructions
-   Multiple unrelated tasks
-   Missing context
-   Missing output format
-   Overly broad questions

------------------------------------------------------------------------

# 9. Python Example

``` python
from openai import OpenAI

client = OpenAI()

prompt = (
    "Explain gradient descent "
    "for a beginner using a simple analogy "
    "in less than 200 words."
)

response = client.responses.create(
    model="gpt-4.1",
    input=prompt
)

print(response.output_text)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Write five prompts on the same topic.
2.  Change one parameter each time.
3.  Compare outputs.
4.  Identify the best prompt.
5.  Explain why it worked better.

------------------------------------------------------------------------

# 11. Interview Questions

### What is Prompt Engineering?

The process of designing prompts that help LLMs produce better
responses.

### Why are prompts important?

Because prompt quality strongly affects response quality.

### What are four important parts of a prompt?

-   Goal
-   Context
-   Constraints
-   Output format

### Is prompt engineering iterative?

Yes. Prompts are refined based on model responses.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Prompt Engineering basics.
-   Prompt anatomy.
-   Best practices.
-   Common mistakes.
-   Python usage.

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 197 -- Zero-Shot Prompting**

You'll learn how LLMs solve completely new tasks without examples and
why zero-shot prompting became one of the defining capabilities of
modern foundation models.
