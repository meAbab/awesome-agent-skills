---
name: unit-test-generator
description: Automatically generate unit tests based on source code, supporting multiple languages and testing frameworks.
license: CC0-1.0
---

# Unit Test Generator

> Automatically generate unit tests based on source code, supporting multiple languages ​​and testing frameworks.
>
> Automatically generate unit tests based on source code, supporting multiple languages and testing frameworks.

## When to Use

Use this skill when the user requests the following actions:
- Generate unit tests
- Write tests for functions/classes
- Create test cases
- Improve code coverage

## Instructions

### Analysis Steps

1. **Identify Code** - Determine the programming language and code structure
2. **Analyzing Functions** - Understand the input, output and behavior of functions/methods
3. **Identify Boundaries** - Identify boundary conditions and edge cases
4. **Select a framework** - Choose an appropriate testing framework based on the language
5. **Generate Tests** - Write comprehensive test cases

### Supported Languages and Frameworks

| Language | Testing Framework |
|------|----------|
| Python | pytest, unittest |
| JavaScript/TypeScript | Jest, Mocha, Vitest |
| Java | JUnit, TestNG |
| Go | testing (built-in) |
| Rust | cargo test (built-in) |

### Test Types

- **Normal Path Test** - Verify expected behavior
- **Boundary Condition Test** - Test boundary values
- **Exception Handling Test** - Verify error handling
- **null value/null input test** - handles null value cases

### Output Format

Use the `templates/test-report.md` template to format the output.

Use the `templates/test-report.md` template to format output.

```markdown
## Unit Test Generation Report

### Analysis Summary
[Code Analysis Summary]

### Generated Tests
[Test code]

### Coverage Notes
- Covered scenarios
- Suggested additional tests
```

## Examples

### Input

```python
def divide(a: float, b: float) -> float:
    if b == 0:
        raise ValueError("Cannot divide by zero")
    return a / b
```

### Output

## Unit test generation report

### Analysis overview
`divide` The function performs a division operation, including a divide-by-zero check. It is necessary to test normal division, division-by-zero exceptions, boundary values, etc.

### Generated test

```python
import pytest
from your_module import divide

class TestDivide:
    """Tests for the divide function."""

    def test_divide_positive_numbers(self):
        """Test division of positive numbers."""
        assert divide(10, 2) == 5.0
        assert divide(7, 2) == 3.5

    def test_divide_negative_numbers(self):
        """Test division with negative numbers."""
        assert divide(-10, 2) == -5.0
        assert divide(10, -2) == -5.0
        assert divide(-10, -2) == 5.0

    def test_divide_by_zero_raises_error(self):
        """Test that dividing by zero raises ValueError."""
        with pytest.raises(ValueError, match="Cannot divide by zero"):
            divide(10, 0)

    def test_divide_zero_numerator(self):
        """Test division when numerator is zero."""
        assert divide(0, 5) == 0.0

    def test_divide_float_precision(self):
        """Test division with floating point numbers."""
        assert divide(1, 3) == pytest.approx(0.333333, rel=1e-5)
```

### Test coverage description
- ✅ Normal division of positive numbers
- ✅ Division of negative numbers
- ✅ Division by zero exception
- ✅ Numerator is zero
- ✅ Floating point precision
