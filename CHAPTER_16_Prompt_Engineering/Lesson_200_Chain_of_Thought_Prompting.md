# Chapter 16 -- Prompt Engineering

# Lesson 200 -- Chain of Thought (CoT) Prompting

> **Chain of Thought (CoT) Prompting is a prompting technique that
> encourages a Large Language Model (LLM) to solve complex problems by
> breaking them into intermediate reasoning steps before arriving at the
> final answer. It is especially effective for mathematics, logical
> reasoning, planning, coding, and multi-step decision-making tasks.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Chain of Thought Prompting.
-   Learn why reasoning improves performance.
-   Compare Zero-Shot CoT and Few-Shot CoT.
-   Design effective reasoning prompts.
-   Understand advantages and limitations.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Chain of Thought?
2.  Why CoT Was Developed
3.  How CoT Works
4.  Zero-Shot vs Few-Shot CoT
5.  Prompt Templates
6.  Applications
7.  Best Practices
8.  Common Mistakes
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is Chain of Thought?

Instead of jumping directly to an answer, the model reasons through
intermediate steps.

``` text
Question
   │
Reasoning Steps
   │
Final Answer
```

Example:

``` text
Question:
A train travels 60 km/h for 2 hours.
How far does it travel?

Reasoning:
Distance = Speed × Time
= 60 × 2
= 120 km

Answer:
120 km
```

------------------------------------------------------------------------

# 2. Why CoT Was Developed

Many problems require multiple logical steps.

Without reasoning:

``` text
Question
   │
Answer
```

With CoT:

``` text
Question
   │
Break into Steps
   │
Solve Each Step
   │
Combine Results
   │
Final Answer
```

This often improves performance on complex tasks.

------------------------------------------------------------------------

# 3. How CoT Works

Typical workflow:

``` text
Prompt
   │
Interpret Problem
   │
Generate Intermediate Reasoning
   │
Verify Relationships
   │
Produce Final Answer
```

CoT does not change the model's weights. It changes how the task is
presented.

------------------------------------------------------------------------

# 4. Zero-Shot vs Few-Shot CoT

## Zero-Shot CoT

A simple instruction encourages reasoning.

``` text
Solve the problem.

Think through the solution step by step.
```

## Few-Shot CoT

Provide worked examples first.

``` text
Example Problem
↓

Reasoning

↓

Answer

New Problem
```

------------------------------------------------------------------------

# 5. Prompt Templates

General template:

``` text
Task:
<problem>

Instructions:
Reason through the problem step by step.

Finally provide the answer separately.
```

Structured output:

``` text
Reasoning:

...

Final Answer:
...
```

------------------------------------------------------------------------

# 6. Applications

-   Mathematics
-   Programming
-   Logical puzzles
-   Scientific reasoning
-   Planning
-   Financial analysis
-   Multi-step workflows

------------------------------------------------------------------------

# 7. Best Practices

-   Clearly define the task.
-   Encourage structured reasoning.
-   Separate reasoning from the final answer.
-   Break large problems into smaller parts.
-   Verify calculations when possible.

------------------------------------------------------------------------

# 8. Common Mistakes

Avoid:

-   Extremely vague instructions
-   Combining unrelated tasks
-   Expecting perfect reasoning for every problem
-   Assuming longer reasoning always means better reasoning

------------------------------------------------------------------------

# 9. Python Example

``` python
from openai import OpenAI

client = OpenAI()

prompt = """
A shop sells 8 notebooks for ₹240.

Reason through the problem step by step.

How much does one notebook cost?

Return the final answer separately.
"""

response = client.responses.create(
    model="gpt-4.1",
    input=prompt
)

print(response.output_text)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Solve five math problems using direct prompting.
2.  Solve the same problems using CoT.
3.  Compare accuracy.
4.  Compare response quality.
5.  Record observations.

------------------------------------------------------------------------

# 11. Interview Questions

### What is Chain of Thought Prompting?

A prompting technique that encourages intermediate reasoning before
producing a final answer.

### Why does CoT improve performance?

Breaking complex problems into smaller reasoning steps reduces ambiguity
and helps the model organize the solution.

### Difference between Zero-Shot CoT and Few-Shot CoT?

Zero-Shot CoT uses only a reasoning instruction, while Few-Shot CoT
includes worked examples.

### Is CoT useful for every task?

No. It is most beneficial for multi-step reasoning tasks such as
mathematics, planning, coding, and logical analysis.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Chain of Thought Prompting
-   Why reasoning helps
-   Zero-Shot vs Few-Shot CoT
-   Prompt templates
-   Applications
-   Python implementation

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 201 -- Tree of Thought (ToT) Prompting**

You'll learn how Tree of Thought expands on Chain of Thought by
exploring multiple reasoning paths simultaneously, evaluating
alternatives, backtracking when necessary, and improving performance on
complex planning and search problems.
