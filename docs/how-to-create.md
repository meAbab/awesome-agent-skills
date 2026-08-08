# How to create Agent Skill

This guide will help you create a standard Agent Skill that can be used on Cursor, Claude, Codex and other platforms.

> 📋 **Specification Document**: See the [SKILL.md specification](skill-spec.md) for complete format specifications and best practices.

## Quick Start

### 1. Create the directory structure

```bash
mkdir my-agent-skill
cd my-agent-skill
```

### 2. Create SKILL.md

This is the core file, telling the AI ​​Agent how to use your skill.

```markdown
---
name: my-agent-skill
description: A brief description of what this skill does.
license: MIT
---

# My Agent Skill

> Briefly describe what this skill does.

## When to Use

describes when this skill should be used.

## Instructions

Detailed usage instructions...

## Examples

Usage examples...
```

#### YAML Frontmatter Description

| Field | Required | Description |
|------|------|------|
| `name` | ✅ | Lowercase letters, separated by hyphens (such as `code-review`) |
| `description` | ✅ | A short description in English describing the skill's functionality and usage scenarios |
| `license` | ❌ | License (e.g. MIT, CC0-1.0, Apache-2.0) |

### 3. Add script (optional)

```bash
mkdir scripts
# Add your script file
```

## Full example

### Directory structure

```
code-review-skill/
├── SKILL.md # Core description file
├── scripts/
│ └── analyze.py # Analysis script
├── templates/
│ └── review-template.md # Review template
└── examples/
    └── sample-review.md # Sample output
```

### SKILL.md sample

```markdown
---
name: code-review
description: Smart code review skill that helps review code quality and provide improvement suggestions.
license: MIT
---

# Code Review Skill

> Intelligent code review skills to help you review code quality, discover potential problems, and provide improvement suggestions.

## When to Use

Use this skill when a user requests the following actions:
- Review code
- Check code quality
- Find problems in code
- Request code improvement suggestions

## Instructions

### Review steps

1. **Read code**: Read the provided code carefully
2. **Check for issues**:
   - syntax error
   - logic problem
   - security risk
   - performance problem
3. **Provide suggestions**: Give specific suggestions for improvement
4. **Output Report**: Use templates to generate audit reports

### Output format

Output review results using the following format:

## Code review report

### Overview
[Brief summary]

### Issues found
- [ ] Question 1
- [ ] Question 2

### Improvement suggestions
1. Suggestion 1
2. Suggestion 2

### Rating
- Code quality: X/10
- Readability: X/10
- Maintainability: X/10

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

### Found issues
- [ ] Function name is not descriptive
- [ ] Missing type hints
- [ ] Missing docstring

### Improvement suggestions
1. Rename the function to `add_numbers`
2. Add type hint
3. Add docstring

### Rating
- Code Quality: 6/10
- Readability: 7/10
- Maintainability: 5/10
```

## Best Practices

### 1. Clear trigger conditions

clearly states when to use this skill in the "When to Use" section:

```markdown
## When to Use

Use this skill when the user:
- Explicitly request "Review Code"
- Say "Help me check this code"
- Ask "What's wrong with this code"
```

### 2. Detailed instructions

Provide instructions with enough detail so that the AI knows what to do at each step:

```markdown
## Instructions

### Step 1: Analyze input
- Determine programming language
- Identify code structure

### Step 2: Perform checks
- Run static analysis
- Check code specifications

### Step 3: Generate report
- Use template format
- Include all findings
```

### 3. Provide an example The

example helps the AI understand the expected input and output:

```markdown
## Examples

### Example 1: Simple function
**Input**: [code]
**Output**: [Result]

### Example 2: Complex class
**Input**: [Code]
**Output**: [Result]
```

### 4. Use template

If the output has a fixed format, provide a template file:

```
templates/
├── report.md
├── summary.md
└── checklist.md
```

## Publish your Skill

1. **Create GitHub repository**
2. **Add README**: explain how to install and use
3. **Submit to this project list**: Submit PR to add to the list

### Recommended README structure

```markdown
# My Skill Name

Short description

## Installation

## Usage

## Example

## License
```

## FAQ

### Q: Does SKILL.md have to be in English?

Not necessarily, both Chinese and English are acceptable. But it is recommended to provide bilingual versions to reach a wider audience.

### Q: Can binary files be included?

Not recommended. Try to use scripts and configurations in text format.

### Q: How do I test my skill?

In Cursor or Claude, put the skill into the corresponding directory, and then try to trigger the usage scenario.

---

## More resources

- [SKILL.md Specification](skill-spec.md) - Complete format specifications and best practices
- [Official Anthropic Skills Repository](https://github.com/anthropics/skills)
- [Awesome Cursor Rules](https://github.com/PatrickJS/awesome-cursorrules)
- [GitHub Copilot Agent Skills Documentation](https://docs.github.com/en/copilot/concepts/agents/about-agent-skills)
