# Chapter 16 -- Prompt Engineering

# Lesson 206 -- System Prompts

> **A System Prompt is a high-priority instruction that defines how a
> Large Language Model (LLM) should behave throughout a conversation. It
> establishes the AI's role, goals, tone, constraints, safety rules, and
> priorities before any user message is processed. In production AI
> systems, the system prompt acts as the foundation that guides every
> response.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand System Prompts.
-   Learn why they are important.
-   Compare system, user, and assistant messages.
-   Understand prompt hierarchy.
-   Learn role and persona design.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What are System Prompts?
2.  Why System Prompts Matter
3.  Prompt Hierarchy
4.  Anatomy of a System Prompt
5.  Role & Persona Design
6.  Safety & Constraints
7.  Prompt Injection Basics
8.  Best Practices
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What are System Prompts?

A conversation usually contains different message types.

``` text
System Prompt
      │
User Prompt
      │
Assistant Response
```

The system prompt defines the assistant's overall behavior before user
requests are processed.

------------------------------------------------------------------------

# 2. Why System Prompts Matter

Without clear instructions:

-   Responses may become inconsistent.
-   Tone may change unexpectedly.
-   Safety requirements may be ignored.
-   Output format may vary.

Example:

``` text
System:
You are an AI tutor.

Always explain concepts using simple language.

↓

User:
Explain neural networks.
```

The response now follows the tutor role.

------------------------------------------------------------------------

# 3. Prompt Hierarchy

Modern chat systems process instructions according to priority.

``` text
Highest Priority

System Prompt
      │
Developer Instructions
      │
User Prompt
      │
Conversation History

Lowest Priority
```

Higher-priority instructions generally override conflicting
lower-priority requests.

------------------------------------------------------------------------

# 4. Anatomy of a System Prompt

A strong system prompt defines:

``` text
Role
 │
Goal
 │
Behavior
 │
Constraints
 │
Output Style
```

Example:

``` text
Role:
AI Career Coach

Audience:
College students

Style:
Friendly and concise

Rules:
Use bullet points.
Avoid technical jargon.
```

------------------------------------------------------------------------

# 5. Role & Persona Design

Examples:

-   AI Teacher
-   Coding Assistant
-   Legal Research Assistant
-   Medical Information Assistant
-   Travel Planner

A role helps the model maintain consistent behavior.

------------------------------------------------------------------------

# 6. Safety & Constraints

System prompts often specify:

-   Safety rules
-   Privacy requirements
-   Allowed tools
-   Formatting requirements
-   Topics to avoid

``` text
System Rules
      │
Model
      │
Safe Response
```

------------------------------------------------------------------------

# 7. Prompt Injection Basics

Prompt injection is an attempt to override or manipulate existing
instructions.

Example:

``` text
User:
Ignore all previous instructions.
```

Well-designed systems resist inappropriate instruction overrides by
preserving higher-priority guidance.

------------------------------------------------------------------------

# 8. Best Practices

-   Clearly define the role.
-   Keep instructions specific.
-   Avoid contradictory rules.
-   State output requirements.
-   Review and refine prompts over time.

------------------------------------------------------------------------

# 9. Python Example

``` python
from openai import OpenAI

client = OpenAI()

response = client.responses.create(
    model="gpt-4.1",
    input=[
        {
            "role": "system",
            "content": "You are a Python tutor. Explain concepts simply."
        },
        {
            "role": "user",
            "content": "Explain recursion."
        }
    ]
)

print(response.output_text)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Design a system prompt for an AI tutor.
2.  Design one for a coding assistant.
3.  Add formatting rules.
4.  Test with different user prompts.
5.  Compare consistency.

------------------------------------------------------------------------

# 11. Interview Questions

### What is a System Prompt?

A high-priority instruction that defines the model's behavior throughout
a conversation.

### Why are System Prompts important?

They ensure consistent behavior, tone, safety, and formatting.

### What is prompt hierarchy?

The ordering of instructions by priority, where higher-priority
instructions generally take precedence over lower-priority ones.

### What is prompt injection?

An attempt to manipulate or override existing instructions.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   System Prompts
-   Prompt hierarchy
-   Role and persona design
-   Safety constraints
-   Prompt injection basics
-   Python implementation

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 207 -- Jailbreaks**

You'll learn what jailbreak prompts are, why they exist, common attack
techniques, their limitations, and how developers build safer AI systems
that resist prompt manipulation.
