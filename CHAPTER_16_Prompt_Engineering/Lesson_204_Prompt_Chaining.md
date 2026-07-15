# Chapter 16 -- Prompt Engineering

# Lesson 204 -- Prompt Chaining

> **Prompt Chaining is a prompt engineering technique where a complex
> task is divided into multiple smaller prompts. The output of one
> prompt becomes the input to the next, creating a structured workflow.
> This approach improves accuracy, modularity, debugging, and
> scalability, making it one of the most widely used patterns in
> production AI systems.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Prompt Chaining.
-   Learn why prompt pipelines improve reliability.
-   Design multi-stage workflows.
-   Compare Prompt Chaining with ReAct.
-   Understand real-world AI pipelines.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Prompt Chaining?
2.  Why Prompt Chaining Was Developed
3.  How Prompt Chaining Works
4.  Types of Prompt Chains
5.  Prompt Chaining vs ReAct
6.  Real-World Applications
7.  Best Practices
8.  Common Mistakes
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is Prompt Chaining?

Instead of solving everything with one prompt, we split the task.

``` text
User Request
      │
Prompt 1
      │
Prompt 2
      │
Prompt 3
      │
Final Output
```

Each prompt performs one focused job.

------------------------------------------------------------------------

# 2. Why Prompt Chaining Was Developed

Large prompts often become:

-   Difficult to debug
-   Hard to maintain
-   Less reliable
-   More expensive

Prompt chaining breaks a large problem into manageable steps.

Example:

``` text
Research Topic
      │
Summarize
      │
Extract Key Points
      │
Generate Report
```

------------------------------------------------------------------------

# 3. How Prompt Chaining Works

General workflow:

``` text
Input
  │
Analyze
  │
Extract Information
  │
Transform
  │
Validate
  │
Generate Final Result
```

Each stage has a clearly defined responsibility.

------------------------------------------------------------------------

# 4. Types of Prompt Chains

## Sequential Chain

``` text
A → B → C → D
```

Each step depends on the previous one.

## Parallel Chain

``` text
      Input
     /  |  \
    A   B   C
      \ | /
     Combine
```

Independent prompts run simultaneously before their outputs are merged.

## Conditional Chain

``` text
Input
  │
Decision
 ├──► Path A
 └──► Path B
```

Different prompts execute depending on earlier results.

------------------------------------------------------------------------

# 5. Prompt Chaining vs ReAct

  Feature               Prompt Chaining   ReAct
  --------------------- ----------------- --------------
  Multiple prompts      ✅                ⚠️ Sometimes
  External tool usage   Optional          Core feature
  Pipeline design       ✅                Limited
  Agent behavior        Possible          Native
  Workflow control      High              Dynamic

Prompt Chaining organizes work into stages, while ReAct emphasizes
alternating reasoning with tool use.

------------------------------------------------------------------------

# 6. Real-World Applications

-   RAG pipelines
-   Document summarization
-   Customer support
-   Data extraction
-   Report generation
-   AI coding assistants
-   Business automation

Example RAG chain:

``` text
Question
   │
Retrieve Documents
   │
Rank Results
   │
Summarize Evidence
   │
Generate Answer
```

------------------------------------------------------------------------

# 7. Best Practices

-   Keep each prompt focused.
-   Validate outputs between stages.
-   Minimize unnecessary steps.
-   Reuse prompts across workflows.
-   Log intermediate outputs for debugging.

------------------------------------------------------------------------

# 8. Common Mistakes

Avoid:

-   Making every step dependent on a fragile output.
-   Overcomplicating simple tasks.
-   Passing ambiguous information between stages.
-   Ignoring validation before the next prompt.

------------------------------------------------------------------------

# 9. Python Example

``` python
step1 = "Summarize the article."

step2 = "Extract five key points from the summary."

step3 = "Write an executive report using those points."

pipeline = [step1, step2, step3]

for step in pipeline:
    print(step)
```

In production, each step would call an LLM and pass its output to the
next stage.

------------------------------------------------------------------------

# 10. Mini Project

1.  Build a document summarization pipeline.
2.  Extract keywords.
3.  Generate FAQs.
4.  Produce a final report.
5.  Compare chained prompts with a single large prompt.

------------------------------------------------------------------------

# 11. Interview Questions

### What is Prompt Chaining?

Breaking a complex task into multiple smaller prompts connected in
sequence or other workflow patterns.

### Why use Prompt Chaining?

It improves modularity, reliability, and debugging.

### What is the difference between Sequential and Parallel chains?

Sequential chains depend on previous outputs, while parallel chains
execute independent prompts simultaneously.

### Is Prompt Chaining used in production AI?

Yes. It is widely used in RAG systems, AI agents, and enterprise
workflows.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Prompt Chaining
-   Workflow patterns
-   Sequential, Parallel, and Conditional chains
-   Comparison with ReAct
-   Best practices
-   Python example

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 205 -- Structured Output**

You'll learn how to make LLMs return reliable JSON, XML, Markdown
tables, and schema-constrained outputs, enabling seamless integration
with APIs, databases, and production software systems.
