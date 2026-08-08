# SKILL.md Specification

This document defines the standard specifications of Agent Skills to help developers create compatible Skills.

This document defines the standard specification for Agent Skills to help developers create compatible Skills.

---

## Table of Contents

- [File Structure](#file-structure)
- [Frontmatter Specification](#frontmatter-specification)
- [Content Structure](#content-structure)
- [Naming Conventions](#naming-conventions)
- [Platform Compatibility](#platform-compatibility)
- [Best Practices](#best-practices)

---

## File Structure

A standard Skill directory structure is as follows:

```
my-skill/
├── SKILL.md # Required
├── README.md # Optional - human-readable description
├── scripts/ # Optional
│   ├── analyze.py
│   └── helper.sh
├── templates/ # Optional
│   └── output-template.md
├── examples/ # Optional
│   └── sample-output.md
└── resources/ # Optional
    └── config.json
```

### File Descriptions

| File/Directory | Required | Description |
|-----------|------|------|
| `SKILL.md` | ✅ | Core command file, AI Agent reads this file to learn how to use Skill |
| `README.md` | ❌ | Human-readable instructions and installation guide |
| `scripts/` | ❌ | Executable script for AI Agent to call |
| `templates/` | ❌ | Output template, define result format |
| `examples/` | ❌ | Usage examples and sample output |
| `resources/` | ❌ | Other resource files (configuration, data, etc.) |

---

## Frontmatter Specification

The SKILL.md file must start with YAML frontmatter, which defines the metadata of the Skill.

### Required Fields

| Field | Type | Description | Example |
|------|------|------|------|
| `name` | string | Unique identifier for the Skill, lowercase letters and hyphens | `code-review` |
| `description` | string | Short English description (< 160 characters recommended) | `Smart code review skill...` |

### Optional Fields

| Field | Type | Description | Example |
|------|------|------|------|
| `license` | string | License identifier | `MIT`, `CC0-1.0`, `Apache-2.0` |
| `version` | string | Semantic version number | `1.0.0` |
| `author` | string | Author or organization name | `Your Name` |
| `homepage` | string | Project homepage URL | `https://github.com/...` |
| `tags` | array | Category tags | `[code, review, quality]` |
| `platforms` | array | Supported platforms | `[cursor, claude, copilot]` |
| `requires` | array | Other dependent Skills | `[git-helper]` |

### Complete Example

```yaml
---
name: code-review
description: Smart code review skill that helps review code quality and provide improvement suggestions.
license: MIT
version: 1.0.0
author: Your Name
homepage: https://github.com/yourname/code-review-skill
tags:
  - code
  - review
  - quality
platforms:
  - cursor
  - claude
  - copilot
---
```

---

## Content Structure

The Markdown content of SKILL.md should contain the following sections:

### Required Sections

#### 1. Title and Description

```markdown
# Skill Name

> Short description (Bilingual Chinese and English is better)
>
> Short description in English
```

#### 2. When to Use

Describes the circumstances under which the AI Agent should activate this Skill:

```markdown
## When to Use

This skill is used when the user requests the following operation:
- Trigger condition 1
- Trigger condition 2
- Trigger condition 3
```

#### 3. Instructions

Detailed usage instructions tell the AI Agent how to perform the task:

```markdown
## Instructions

### Step 1
Detailed instructions...

### Step 2
Detailed instructions...
```

### Recommended Sections

#### 4. Examples

Input and output examples to help AI understand expected behavior:

```markdown
## Examples

### Input
[Example input]

### Output
[Example output]
```

#### 5. Configuration (if required)

```markdown
## Configuration

Configurable options and parameters...
```

---

## Naming Conventions

### Skill Name

- Use lowercase letters
- Separate words with hyphens `-`
- Concise and descriptive
- Avoid using common words

✅ Correct example:
- `code-review`
- `git-commit-helper`
- `api-doc-generator`
- `unit-test-generator`

❌ Bad example:
- `CodeReview` (do not use camel case)
- `code_review` (don't use underscores)
- `my-skill` (too generic)
- `helper` (not descriptive enough)

### File naming

- Skill core files must be named `SKILL.md` (uppercase)
- Script files use lowercase letters and hyphens or underscores
- Template files use descriptive names

---

## Platform Compatibility

### Directory Locations

| Platform | Global Directory | Project Directory |
|------|----------|----------|
| Cursor | `~/.cursor/skills/` | `.cursor/skills/` |
| Claude Code | `~/.claude/skills/` | `.claude/skills/` |
| GitHub Copilot | `~/.copilot/skills/` | `.github/skills/` |
| Windsurf | `~/.windsurf/skills/` | `.windsurf/skills/` |
| OpenAI Codex | `~/.codex/skills/` | `.codex/skills/` |

### Compatibility Notes

1. **File encoding**: Use UTF-8 encoding
2. **Line break**: Use LF (`\n`), avoid CRLF
3. **Script permission**: Make sure the script has execution permission (`chmod +x`)
4. **Path Reference**: Use relative paths to reference files within the Skill

---

## Best Practices

### 1. Clear trigger conditions

Clearly define when to use this Skill and avoid vague descriptions:

```markdown
## When to Use

✅ Good examples:
- when the user says "review this code"
- when the user asks "check the code quality for me"

❌ bad examples:
- when you need help
- when programming
```

### 2. Step-by-step instructions

Break down complex tasks into clear steps:

```markdown
## Instructions

### Step 1: Analyze the input
- Determine the programming language
- Identify the code structure

### Step 2: Perform checks
- Check for syntax errors
- Check for logic problems

### Step 3: Generate report
- uses the standard format
- contains all findings
```

### 3. Provide an example

Examples help the AI understand expected input and output formats:

```markdown
## Examples

### Example 1: Simple function
**Input**:
```python
def add(a, b):
    return a + b
```

**Output**:
[Expected review results]
```

### 4. Use template

If the output has a fixed format, provide a template file and reference it in Instructions:

```markdown
## Instructions

Use the template in `templates/report.md` to format the output.
```

### 5. Support bilingual

In order to gain a wider user base, it is recommended to provide bilingual content in Chinese and English:

```markdown
# Code Review

> Intelligent code review skills
>
> Smart code review skill
```

---

## Version Compatibility

This specification version: `1.0.0`

### Change history

| Version | Date | Changes |
|------|------|------|
| 1.0.0 | 2025-01 | Initial version |

---

## References

- [Official Agent Skills Specification](https://skill.md/)
- [agentskills.io Specification](https://agentskills.io/specification)
- [Anthropic Skills Repository](https://github.com/anthropics/skills)
- [How to Create a Skill](how-to-create.md)
