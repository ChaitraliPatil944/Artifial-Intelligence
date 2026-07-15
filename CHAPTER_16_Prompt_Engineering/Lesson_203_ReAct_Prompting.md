# Chapter 16 -- Prompt Engineering

# Lesson 203 -- ReAct (Reason + Act) Prompting

> **ReAct (Reason + Act) Prompting is a prompting framework that enables
> Large Language Models (LLMs) to alternate between reasoning and taking
> actions. Instead of relying only on internal knowledge, the model can
> decide to use external tools such as search engines, calculators,
> APIs, databases, or code interpreters, observe the results, and
> continue reasoning until it reaches a solution. ReAct is one of the
> foundations of modern AI agents.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand ReAct Prompting.
-   Learn why ReAct was developed.
-   Study the Thought → Action → Observation cycle.
-   Learn how LLMs use external tools.
-   Compare ReAct with Chain of Thought.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is ReAct?
2.  Why ReAct Was Developed
3.  ReAct Workflow
4.  Thought--Action--Observation Loop
5.  ReAct vs Chain of Thought
6.  Tool Usage
7.  Applications
8.  Best Practices
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is ReAct?

ReAct combines **reasoning** with **actions**.

``` text
User Question
      │
Thought
      │
Action
      │
Observation
      │
Reason Again
      │
Final Answer
```

The model decides when additional information or computation is needed.

------------------------------------------------------------------------

# 2. Why ReAct Was Developed

Traditional prompting has limitations.

``` text
Question
   │
Reason
   │
Answer
```

If the model lacks information, it may produce an incorrect answer.

ReAct allows the model to gather evidence before answering.

------------------------------------------------------------------------

# 3. ReAct Workflow

``` text
Problem
   │
Think
   │
Choose Tool
   │
Execute Tool
   │
Observe Result
   │
Continue Reasoning
   │
Answer
```

------------------------------------------------------------------------

# 4. Thought--Action--Observation Loop

Example:

``` text
Question:
What is today's exchange rate?

Thought:
I need current information.

Action:
Search exchange rate API.

Observation:
1 USD = 0.86 EUR

Answer:
Today's exchange rate is approximately...
```

------------------------------------------------------------------------

# 5. ReAct vs Chain of Thought

  Feature               Chain of Thought   ReAct
  --------------------- ------------------ -----------
  Internal reasoning    ✅                 ✅
  External tools        ❌                 ✅
  Live information      ❌                 ✅
  Multi-step planning   ✅                 ✅
  Agent workflows       Limited            Excellent

------------------------------------------------------------------------

# 6. Tool Usage

Typical tools include:

-   Web Search
-   Calculator
-   Python
-   SQL Databases
-   APIs
-   Vector Databases
-   File Systems

``` text
LLM
 │
 ├── Search
 ├── Calculator
 ├── Database
 └── API
```

------------------------------------------------------------------------

# 7. Applications

-   AI Agents
-   Customer Support
-   Research Assistants
-   Coding Assistants
-   Financial Analysis
-   Scientific Research
-   RAG Systems

------------------------------------------------------------------------

# 8. Best Practices

-   Give the model access only to necessary tools.
-   Validate tool outputs.
-   Keep tool descriptions clear.
-   Limit unnecessary tool calls.
-   Log reasoning and actions for debugging.

------------------------------------------------------------------------

# 9. Python Example

``` python
from openai import OpenAI

client = OpenAI()

prompt = """
Answer the question.

If additional information is required,
describe which tool you would use,
what you expect to observe,
and then provide the final answer.
"""

response = client.responses.create(
    model="gpt-4.1",
    input=prompt
)

print(response.output_text)
```

In production, frameworks such as LangGraph or similar agent frameworks
execute the selected tools.

------------------------------------------------------------------------

# 10. Mini Project

1.  Build a simple AI assistant.
2.  Add calculator support.
3.  Add web search.
4.  Answer factual questions.
5.  Record each Thought → Action → Observation step.

------------------------------------------------------------------------

# 11. Interview Questions

### What does ReAct stand for?

Reason + Act.

### Why is ReAct important?

It allows LLMs to combine reasoning with external tools.

### What is the Observation step?

The information returned by a tool after an action is executed.

### Where is ReAct commonly used?

AI agents, RAG systems, coding assistants, and enterprise automation.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   ReAct Prompting
-   Thought--Action--Observation loop
-   Tool usage
-   ReAct vs Chain of Thought
-   Applications
-   Python example

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 204 -- Prompt Chaining**

You'll learn how to decompose large problems into a sequence of smaller
prompts, build multi-stage LLM workflows, and improve reliability
through modular prompt pipelines.
