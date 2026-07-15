# Chapter 16 -- Prompt Engineering

# Lesson 202 -- Self-Consistency Prompting

> **Self-Consistency Prompting is an advanced prompting technique that
> improves reasoning accuracy by generating multiple independent
> reasoning paths for the same problem and selecting the answer that
> appears most consistently. Instead of relying on a single Chain of
> Thought, the model samples several reasoning chains and chooses the
> final answer through majority agreement.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Self-Consistency Prompting.
-   Learn why it was developed.
-   Study how multiple reasoning paths improve accuracy.
-   Compare Self-Consistency with Chain of Thought.
-   Explore practical applications.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Self-Consistency?
2.  Why Self-Consistency Was Developed
3.  How It Works
4.  Self-Consistency vs Chain of Thought
5.  Majority Voting
6.  Applications
7.  Best Practices
8.  Common Mistakes
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is Self-Consistency Prompting?

Instead of trusting one reasoning chain, the model explores several.

``` text
Question
   │
 ├── Reasoning Path 1
 ├── Reasoning Path 2
 ├── Reasoning Path 3
 ├── Reasoning Path 4
 └── Reasoning Path 5
          │
   Compare Answers
          │
 Majority Voting
          │
    Final Answer
```

The assumption is that the correct answer is more likely to appear
repeatedly across independent reasoning attempts.

------------------------------------------------------------------------

# 2. Why Self-Consistency Was Developed

Chain of Thought significantly improved reasoning, but a **single
reasoning path can still contain mistakes**.

Example:

``` text
Question
   │
One Chain of Thought
   │
Wrong Calculation
   │
Wrong Answer
```

Self-Consistency reduces this risk by considering multiple solutions
before deciding.

------------------------------------------------------------------------

# 3. How It Works

General workflow:

``` text
Problem
   │
Generate Multiple CoT Paths
   │
Independent Reasoning
   │
Collect Answers
   │
Majority Vote
   │
Final Prediction
```

Each reasoning path is generated independently, often using stochastic
sampling.

------------------------------------------------------------------------

# 4. Self-Consistency vs Chain of Thought

  Feature              Chain of Thought   Self-Consistency
  -------------------- ------------------ --------------------
  Reasoning Paths      One                Multiple
  Final Answer         Single chain       Majority agreement
  Accuracy             High               Often Higher
  Computational Cost   Lower              Higher
  Reliability          Good               Better

------------------------------------------------------------------------

# 5. Majority Voting

Suppose five reasoning paths produce:

``` text
Path 1 → 42
Path 2 → 42
Path 3 → 39
Path 4 → 42
Path 5 → 42
```

Result:

``` text
42 wins (4/5 votes)
```

The most frequent answer becomes the final prediction.

------------------------------------------------------------------------

# 6. Applications

-   Mathematical reasoning
-   Logical puzzles
-   Scientific problem solving
-   Coding
-   Planning
-   Financial calculations
-   Multi-step decision making

------------------------------------------------------------------------

# 7. Best Practices

-   Generate diverse reasoning paths.
-   Use enough samples for meaningful voting.
-   Apply to complex reasoning tasks.
-   Verify important outputs independently when possible.

------------------------------------------------------------------------

# 8. Common Mistakes

Avoid:

-   Using only one reasoning path.
-   Too few samples.
-   Applying Self-Consistency to trivial tasks where the extra
    computation offers little benefit.
-   Assuming majority voting guarantees correctness.

------------------------------------------------------------------------

# 9. Python Example

``` python
from openai import OpenAI

client = OpenAI()

prompt = """
Solve the following math problem.

Generate several independent solution paths.

Choose the answer that appears most consistently.
"""

response = client.responses.create(
    model="gpt-4.1",
    input=prompt
)

print(response.output_text)
```

*In production systems, multiple sampled responses are typically
generated programmatically and compared.*

------------------------------------------------------------------------

# 10. Mini Project

1.  Select 20 math problems.
2.  Solve using standard prompting.
3.  Solve using Chain of Thought.
4.  Solve using Self-Consistency.
5.  Compare accuracy and reasoning quality.

------------------------------------------------------------------------

# 11. Interview Questions

### What is Self-Consistency Prompting?

A prompting strategy that generates multiple reasoning paths and selects
the most consistent answer.

### Why is it better than standard Chain of Thought?

It reduces the impact of errors from any single reasoning chain.

### What is majority voting?

Choosing the answer that appears most frequently across multiple
independent reasoning paths.

### What is the biggest drawback?

Higher computational cost because multiple reasoning chains must be
generated.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Self-Consistency Prompting
-   Multiple reasoning paths
-   Majority voting
-   Comparison with Chain of Thought
-   Applications
-   Python implementation

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 203 -- ReAct (Reason + Act) Prompting**

You'll learn how ReAct combines reasoning with external actions such as
tool use, web search, calculators, APIs, and databases, enabling LLMs to
interact with the outside world instead of relying solely on internal
knowledge.
