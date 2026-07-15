# Chapter 16 -- Prompt Engineering

# Lesson 205 -- Structured Output

> **Structured Output is the practice of instructing a Large Language
> Model (LLM) to generate responses in a predefined format such as JSON,
> XML, YAML, CSV, Markdown tables, or another schema. Instead of
> producing free-form text, the model returns machine-readable data that
> can be reliably consumed by applications, APIs, databases, and
> automation workflows.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand Structured Output.
-   Learn why structured responses matter.
-   Explore common output formats.
-   Understand schema validation.
-   Learn best practices for production AI.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Structured Output?
2.  Why Structured Output Matters
3.  Common Output Formats
4.  Schema-Constrained Generation
5.  Validation
6.  Real-World Applications
7.  Best Practices
8.  Common Mistakes
9.  Python Example
10. Mini Project
11. Interview Questions
12. Summary
13. What's Next?

------------------------------------------------------------------------

# 1. What is Structured Output?

Instead of:

``` text
The user's name is Alice and she is 25 years old.
```

Return:

``` json
{
  "name": "Alice",
  "age": 25
}
```

``` text
User Prompt
      │
LLM
      │
Structured Data
```

------------------------------------------------------------------------

# 2. Why Structured Output Matters

Free-form text is difficult for software to process.

Structured output enables:

-   Reliable parsing
-   API integration
-   Database storage
-   Automation
-   Validation

Example:

``` text
LLM
 │
 JSON
 │
 Backend
 │
 Database
```

------------------------------------------------------------------------

# 3. Common Output Formats

## JSON

``` json
{
  "title":"AI",
  "difficulty":"Beginner"
}
```

## XML

``` xml
<course>
  <title>AI</title>
</course>
```

## YAML

``` yaml
title: AI
difficulty: Beginner
```

## CSV

``` text
Name,Age
Alice,25
Bob,30
```

## Markdown Table

  Name      Age
  ------- -----
  Alice      25
  Bob        30

------------------------------------------------------------------------

# 4. Schema-Constrained Generation

Define exactly what fields are allowed.

``` text
Schema
   │
LLM
   │
Valid JSON
```

Example schema:

``` text
Person
├── name (string)
├── age (integer)
└── city (string)
```

This reduces ambiguity and makes downstream processing more reliable.

------------------------------------------------------------------------

# 5. Validation

Even structured outputs should be validated.

Checks include:

-   Required fields
-   Data types
-   Value ranges
-   Missing values

``` text
LLM Output
     │
Validator
     │
Valid?
 ├── Yes → Continue
 └── No  → Retry
```

------------------------------------------------------------------------

# 6. Real-World Applications

-   AI agents
-   REST APIs
-   Database ingestion
-   Report generation
-   Workflow automation
-   Data extraction
-   RAG pipelines

------------------------------------------------------------------------

# 7. Best Practices

-   Explicitly specify the format.
-   Define required fields.
-   Keep schemas simple.
-   Validate every response.
-   Retry invalid outputs when necessary.

------------------------------------------------------------------------

# 8. Common Mistakes

Avoid:

-   Mixing prose with JSON.
-   Omitting required fields.
-   Using inconsistent key names.
-   Assuming every output is valid.

------------------------------------------------------------------------

# 9. Python Example

``` python
from openai import OpenAI

client = OpenAI()

prompt = """
Return ONLY valid JSON.

Fields:
name
age
city

Person:
Alice, 25, Pune
"""

response = client.responses.create(
    model="gpt-4.1",
    input=prompt
)

print(response.output_text)
```

------------------------------------------------------------------------

# 10. Mini Project

1.  Extract customer information from emails.
2.  Return JSON.
3.  Validate the JSON.
4.  Store it in a database.
5.  Handle invalid responses with retries.

------------------------------------------------------------------------

# 11. Interview Questions

### What is Structured Output?

Generating responses in a predefined machine-readable format.

### Why is JSON commonly used?

It is lightweight, easy to parse, and widely supported.

### Why validate LLM outputs?

Models can still produce malformed or incomplete structured data.

### Where is Structured Output used?

APIs, AI agents, automation, databases, and production AI systems.

------------------------------------------------------------------------

# 12. Summary

You learned:

-   Structured Output
-   JSON, XML, YAML, CSV
-   Schema-constrained generation
-   Validation
-   Best practices
-   Python implementation

------------------------------------------------------------------------

# 13. What's Next?

**Lesson 206 -- System Prompts**

You'll learn how system prompts define an AI assistant's behavior,
priorities, tone, constraints, and role, and why they form the
foundation of production-grade conversational AI systems.
