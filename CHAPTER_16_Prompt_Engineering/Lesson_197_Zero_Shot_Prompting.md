# Chapter 16 -- Prompt Engineering

# Lesson 197 -- Zero-Shot Prompting

> **Zero-Shot Prompting is a prompting technique where a Large Language
> Model (LLM) performs a task using only instructions, without being
> shown any examples.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Zero-Shot Prompting.
-   Learn why it works.
-   Design effective prompts.
-   Know its strengths and limitations.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Zero-Shot Prompting?
2.  Why Zero-Shot Works
3.  Prompt Structure
4.  Examples
5.  Applications
6.  Best Practices
7.  Common Mistakes
8.  Python Example
9.  Mini Project
10. Interview Questions
11. Summary
12. What's Next?

------------------------------------------------------------------------

# 1. What is Zero-Shot Prompting?

The model receives only instructions.

``` text
Prompt
   │
LLM
   │
Answer
```

Example:

``` text
Classify the sentiment:

"I loved this movie."

Return only:
Positive or Negative.
```

------------------------------------------------------------------------

# 2. Why Zero-Shot Works

Modern LLMs learn broad language patterns during pretraining.

They use:

-   Instructions
-   Context
-   Prior knowledge
-   Statistical language patterns

to solve new tasks.

------------------------------------------------------------------------

# 3. Prompt Structure

``` text
Goal
 │
Context
 │
Constraints
 │
Output Format
```

------------------------------------------------------------------------

# 4. Examples

### Translation

``` text
Translate to French:

Good Morning
```

### Classification

``` text
Classify:

"The service was terrible."

Output:
Positive
Negative
Neutral
```

### Summarization

``` text
Summarize this article in 100 words.
```

------------------------------------------------------------------------

# 5. Applications

-   Translation
-   Summarization
-   Classification
-   Information Extraction
-   Question Answering
-   Code Explanation

------------------------------------------------------------------------

# 6. Best Practices

-   Be specific.
-   Define the audience.
-   Specify output format.
-   Keep one task per prompt.
-   Add constraints.

------------------------------------------------------------------------

# 7. Common Mistakes

Avoid:

-   Vague prompts
-   Missing context
-   Multiple unrelated requests
-   Missing output requirements

------------------------------------------------------------------------

# 8. Python Example

``` python
from openai import OpenAI

client = OpenAI()

prompt = "Classify the sentiment: 'I absolutely loved this book.' Return only Positive, Negative or Neutral."

response = client.responses.create(
    model="gpt-4.1",
    input=prompt
)

print(response.output_text)
```

------------------------------------------------------------------------

# 9. Mini Project

1.  Write five zero-shot prompts.
2.  Test summarization.
3.  Test translation.
4.  Test sentiment analysis.
5.  Compare outputs.

------------------------------------------------------------------------

# 10. Interview Questions

### What is Zero-Shot Prompting?

Using only instructions without providing examples.

### Why does it work?

Because pretrained LLMs generalize from prior learning.

### When is it useful?

Simple or familiar tasks.

### Main limitation?

Reduced accuracy for complex or specialized tasks.

------------------------------------------------------------------------

# 11. Summary

You learned:

-   Zero-Shot Prompting
-   Prompt structure
-   Applications
-   Best practices
-   Python implementation

------------------------------------------------------------------------

# 12. What's Next?

**Lesson 198 -- One-Shot Prompting**

You'll learn how a single demonstration can improve model accuracy for
structured and ambiguous tasks.
