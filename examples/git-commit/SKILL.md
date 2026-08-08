---
name: git-commit
description: Git commit message generator that creates conventional commit messages based on code changes.
license: CC0-1.0
---

# Git Commit

> Git commit message generation skills, automatically generate standardized commit messages based on code changes.
>
> Git commit message generator that creates conventional commit messages based on code changes.

## When to Use

Use this skill when the user requests the following actions:
- Generate commit message
- Write commit message
- Commit code
- Describe code changes

## Instructions

### Commit Message Format

Follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

| Type | Description |
|------|---------------------|
| feat | New feature |
| fix | Bug fix |
| docs | Documentation |
| style | Formatting |
| refactor | Refactoring |
| perf | Performance |
| test | Tests |
| chore | Build/tools |

### Generation Steps

1. **Analyze Changes** - View `git diff` or `git status`
2. **Determine type** - Select the appropriate type
based on the change content 3. **Extraction scope** - Determine the affected modules or components
4. **Write topic** - Describe the change in concise language (within 50 characters)
5. **Add text** - If necessary, detail the reason and impact of the change

### Rules

- Subject line should not exceed 50 characters
- Use imperative sentences (such as "add" instead of "added")
- Start the subject line in lowercase
- Do not end the subject line with a period
- The text should not exceed 72 characters per line

## Examples

### Example 1: New feature

```
feat(auth): add OAuth2 login support

- Add Google OAuth2 provider
- Add GitHub OAuth2 provider
- Update login page with social login buttons
```

### Example 2: Bug fix

```
fix(api): resolve null pointer in user service

The getUserById method was not handling the case when
user doesn't exist, causing a NullPointerException.

Closes #123
```

### Example 3: Documentation update

```
docs(readme): update installation instructions

Add Docker setup guide and clarify environment variables.
```

### Example 4: Refactoring

```
refactor(database): migrate from callbacks to async/await

Convert all database operations to use async/await pattern
for better readability and error handling.
```
