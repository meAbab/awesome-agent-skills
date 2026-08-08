# How to use Agent Skills

This guide describes how to install and use Agent Skills on different platforms.

## Supported platforms

| Platform | Support status | Global directory | Project directory |
|------|---------|---------|---------|
| Cursor | ✅ | `~/.cursor/skills/` | `.cursor/skills/` |
| Claude Code | ✅ | `~/.claude/skills/` | `.claude/skills/` |
| GitHub Copilot | ✅ | `~/.copilot/skills/` | `.github/skills/` |
| Windsurf | ✅ | `~/.windsurf/skills/` | `.windsurf/skills/` |
| OpenAI Codex | ✅ | `~/.codex/skills/` | `.codex/skills/` |

## Installation method

### Method 1: Manual installation

1. Download or clone the skill repository
2. Copy the skill folder to the corresponding directory

```bash
# Example: Install code-review skill to Cursor
git clone https://github.com/example/code-review-skill.git
cp -r code-review-skill ~/.cursor/skills/
```

### Method 2: Use Git Submodule

is suitable for project-level skills:

```bash
# In the project root directory
mkdir -p .cursor/skills
cd .cursor/skills
git submodule add https://github.com/example/code-review-skill.git
```

### Method 3: Use the Skill installer (if available)

Some platforms provide built-in skill installation functions:

```bash
# Codex CLI
codex skill install code-review

# Or use the conversation mode
# "Please help me install code-review skill"
```

## Global vs project level

### Global Skills

- Position: `~/.cursor/skills/` or `~/.codex/skills/`
- Valid for all projects
- Suitable for general tool skills

### Project-level Skills

- Location: `.cursor/skills/` or `.codex/skills/` (in the project root directory)
- Only effective for the current project
- Suitable for project-specific skills
- Can be committed to Git and shared with the team

## Verify installation

Once installed, it can be verified by:

### 1. Check the directory

```bash
ls ~/.cursor/skills/
# You should see the skill folder you installed
```

### 2. Test using

and try to trigger the skill in the AI conversation:

```
User: Please help me review this code
AI: [If the code-review skill is installed correctly, it will be output in the skill's format]
```

## Manage Skills

### View installed Skills

```bash
# Cursor
ls ~/.cursor/skills/

# Codex
ls ~/.codex/skills/
```

### Update Skill

```bash
cd ~/.cursor/skills/code-review-skill
git pull
```

### Delete Skill

```bash
rm -rf ~/.cursor/skills/code-review-skill
```

## Priority Description

When the skill with the same name exists in both the global and project directories:

1. **Project level priority**: The skill in the project directory is given priority
2. **Overridable**: The project can use a customized version to overwrite the global skill

## FAQ

### Q: Skill does not take effect after installation?

Check the following points:
1. Whether the directory name is correct
2. Whether the SKILL.md file exists
3. Whether the file permissions are correct
4. Restart the IDE and try

### Q: How to know that the skill is correctly recognized?

Try asking in the conversation:
```
Can you use [skill-name]?
```

### Q: What should I do if multiple skills conflict?

- Check if the skill's trigger conditions overlap
- Explicitly specify the skill to use when requesting
- Adjust the "When to Use" section of the skill

## Recommended directory structure

```
~/.cursor/
└── skills/
    ├── code-review/
    │   ├── SKILL.md
    │   └── templates/
    ├── git-workflow/
    │   └── SKILL.md
    └── doc-generator/
        ├── SKILL.md
        └── scripts/
```

---

## Next step

- [Create Your Own Skill](how-to-create.md)
- [Browse the Skills List](../README.md#skills-list)
