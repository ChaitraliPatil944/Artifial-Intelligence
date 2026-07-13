# Chapter 14 -- NLP Fundamentals

# Lesson 174 -- Text Cleaning

> **Text Cleaning is the process of removing unnecessary, noisy, or
> inconsistent information from raw text before it is used by an NLP
> model. Clean text improves data quality, reduces vocabulary size,
> speeds up training, and often leads to better model performance.**

------------------------------------------------------------------------

# Learning Objectives

-   Understand why text cleaning is important.
-   Learn common text cleaning techniques.
-   Know when not to remove information.
-   Build a reusable preprocessing pipeline.
-   Prepare for interviews.

------------------------------------------------------------------------

# Table of Contents

1.  What is Text Cleaning?
2.  Why Text Cleaning Matters
3.  Common Sources of Noise
4.  Text Cleaning Pipeline
5.  Cleaning Techniques
6.  When NOT to Clean
7.  Python Implementation
8.  Best Practices
9.  Mini Project
10. Interview Questions
11. Summary
12. What's Next?

------------------------------------------------------------------------

# 1. What is Text Cleaning?

Raw text collected from websites, emails, or social media usually
contains unwanted information.

Example:

``` text
Hey!!! Visit https://example.com 😊😊
```

Cleaned version:

``` text
hey visit
```

------------------------------------------------------------------------

# 2. Why Text Cleaning Matters

Benefits:

-   Improves model accuracy
-   Reduces vocabulary size
-   Removes irrelevant information
-   Speeds up training
-   Produces consistent text

------------------------------------------------------------------------

# 3. Common Sources of Noise

-   HTML tags
-   URLs
-   Email addresses
-   Emojis
-   Punctuation
-   Numbers (task dependent)
-   Extra spaces
-   Duplicate characters
-   Special symbols

------------------------------------------------------------------------

# 4. Text Cleaning Pipeline

``` text
Raw Text
   │
Lowercase
   │
Remove HTML
   │
Remove URLs
   │
Remove Punctuation
   │
Remove Special Characters
   │
Normalize Spaces
   │
Clean Text
```

------------------------------------------------------------------------

# 5. Cleaning Techniques

## Convert to Lowercase

``` text
HELLO World

↓

hello world
```

## Remove HTML

``` text
<p>Hello</p>

↓

Hello
```

## Remove URLs

``` text
Visit https://openai.com

↓

Visit
```

## Remove Emails

``` text
abc@example.com

↓

(remove)
```

## Remove Punctuation

``` text
Hello!!!

↓

Hello
```

## Normalize Whitespaces

``` text
Hello      World

↓

Hello World
```

------------------------------------------------------------------------

# 6. When NOT to Clean

Avoid removing information blindly.

Examples:

-   Keep punctuation for grammar correction.
-   Keep emojis for sentiment analysis if they carry meaning.
-   Keep numbers for financial or medical datasets.
-   Keep capitalization for Named Entity Recognition (NER) when useful.

Cleaning should depend on the task.

------------------------------------------------------------------------

# 7. Python Implementation

``` python
import re
from bs4 import BeautifulSoup

text = "<p>Hello!!! Visit https://example.com 😊</p>"

# Remove HTML
text = BeautifulSoup(text, "html.parser").get_text()

# Lowercase
text = text.lower()

# Remove URLs
text = re.sub(r"http\\S+", "", text)

# Remove punctuation
text = re.sub(r"[^\w\s]", "", text)

# Remove extra spaces
text = re.sub(r"\s+", " ", text).strip()

print(text)
```

Output:

``` text
hello visit
```

------------------------------------------------------------------------

# 8. Best Practices

-   Design cleaning for your specific task.
-   Apply identical preprocessing to training and inference.
-   Save preprocessing code with the model.
-   Test whether each cleaning step actually improves performance.

------------------------------------------------------------------------

# 9. Mini Project

1.  Download 1,000 product reviews.
2.  Remove HTML, URLs, and punctuation.
3.  Normalize whitespace.
4.  Compare vocabulary size before and after cleaning.
5.  Explain which cleaning steps were beneficial.

------------------------------------------------------------------------

# 10. Interview Questions

### Why is text cleaning important?

It removes noise and improves the quality of data used by NLP models.

### Should every punctuation mark be removed?

No. It depends on the application.

### Why convert text to lowercase?

To treat words like "AI" and "ai" consistently when case is not
important.

### Name three common text cleaning operations.

-   Remove HTML
-   Remove URLs
-   Remove punctuation

------------------------------------------------------------------------

# 11. Summary

You learned:

-   What text cleaning is.
-   Common sources of noisy text.
-   Standard preprocessing techniques.
-   Situations where cleaning should be limited.
-   Python implementation.

------------------------------------------------------------------------

# 12. What's Next?

**Lesson 175 -- Tokenization**

You'll learn how text is broken into words, subwords, or characters,
compare different tokenization methods, understand why tokenization is
fundamental to modern NLP, and explore tokenizers used by today's Large
Language Models.
