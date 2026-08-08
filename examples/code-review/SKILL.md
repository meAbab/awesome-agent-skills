---
name: code-review
description: Smart code review skill that helps review code quality, identify potential issues, and provide improvement suggestions.
license: CC0-1.0
---

# Code Review

> Intelligent code review skills help review code quality, identify potential problems, and provide improvement suggestions.
>
> Smart code review skill that helps review code quality, identify potential issues, and provide improvement suggestions.

## When to Use

Use this skill when the user requests the following actions:
- Review code
- Check code quality
- Find issues in code
- Request improvement suggestions

## Instructions

### Review Steps

1. **Read the Code** - Read the provided code carefully
2. **Check for issues**:
   - Syntax errors
   - Logic issues
   - Security vulnerabilities
   - Performance issues
   - Code style
3. **Provide Suggestions** - Give specific suggestions for improvement
4. **Output Report** - Generate a review report using the standard format

### Output Format

```markdown
## Code Review Report

### Summary
[Brief summary]

### Issues Found
- [ ] Issue 1
- [ ] Issue 2

### Improvement Suggestions
1. Suggestion 1
2. Suggestion 2

### Score
- Code Quality: X/10
- Readability: X/10
- Maintainability: X/10
```

## Examples

### Input

```python
def calc(x,y):
    return x+y
```

### Output

## Code review report

### Overview
Simple addition function, there are naming and formatting issues.

### Issues found
- [ ] Function name `calc` is not descriptive
- [ ] missing type hints
- [ ] missing docstring
- Missing spaces around [ ] operator

### Improvement suggestions
1. Rename the function to `add_numbers`
2. Add type hint: `def add_numbers(x: int, y: int) -> int:`
3. Add docstring to describe the function purpose
4. Follow PEP 8 format specification

### Rating
- Code quality: 6/10
- Readability: 7/10
- Maintainability: 5/10
