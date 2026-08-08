# Contributing Guide


Thanks for your interest in contributing to Awesome Agent Skills!

### How to Contribute

#### Adding a New Entry

1. **Fork** this repository
2. Find the appropriate category in both README.md and README_ZH.md
3. Add your entry following the format:

```markdown
| skill-name | Short description | Platform | [GitHub](URL) |
```

4. Submit a **Pull Request**

> The online search page is generated automatically from `README.md` and `README_ZH.md` by GitHub Actions after PRs are merged. No manual search-index edits are required.

### Inclusion Requirements

#### General Requirements

- [ ] Entry must be publicly accessible
- [ ] Description must be clear and accurate
- [ ] Link must be valid
- [ ] Must update both `README.md` and `README_ZH.md` (keep bilingual READMEs in sync)
- [ ] Please verify formatting before submitting — PRs that break existing document structure will be rejected
- [ ] Prefer existing categories; do not create a standalone section for a single project

#### By Entry Type

- [ ] Community submissions should have at least **64 GitHub Stars** by default; maintainers may make explicit exceptions for special cases
- [ ] Single Skill repositories: must contain a `SKILL.md` file and meet the community stars threshold
- [ ] Skills collections / managers / installers: must clearly serve skill discovery, installation, sync, distribution, or management; `SKILL.md` at the repo root is not required, but the repository must meet the community stars threshold
- [ ] Official Resources: may be exempt from the stars threshold, but must be official projects, official docs, or widely recognized ecosystem infrastructure

#### Recommended

- [ ] Open source projects preferred
- [ ] Provide bilingual description (English/Chinese)
- [ ] Include usage examples
- [ ] Commercial product wrappers typically require higher community validation
- [ ] Third-party hosted trials / demos should clearly document runtime behavior, data handling, privacy policy, and maintenance responsibility; external services that process user code, diffs, logs, or credentials are generally not linked directly from the README

### Format Guidelines

#### Skill Entry Format

```markdown
| Name | Description | Platform | Link |
|------|-------------|----------|------|
| my-skill | Short description of what it does (10-20 words) | All | [Link](https://github.com/...) |
```

#### Platform Labels

- `All` - Supports all platforms
- `Cursor` - Cursor only
- `Claude` - Claude only
- `Copilot` - GitHub Copilot only
- `Windsurf` - Windsurf only
- `Codex` - Codex only
- `OpenCode` - OpenCode only
- `OpenClaw` - OpenClaw only
- Multiple platforms separated by `/`: `Cursor/Claude`

### Categories

| Category | Description |
|----------|-------------|
| Official Resources | Officially maintained resources, docs, and ecosystem infrastructure |
| Skills Collections | Repositories containing multiple skills, plus skill managers/installers |
| Development Tools | Code review, debugging, testing, etc. |
| Productivity | General productivity tools |
| Writing | Documentation, articles |
| Data Processing | Data analysis, transformation |
| DevOps | Deployment, operations |
| Design | UI/UX design |

If your entry doesn't fit existing categories, feel free to suggest a new one in your PR.

### PR Template

Please include the following information when submitting a PR:

```markdown
## Add Entry

**Name**:
**Link**:
**Description**:
**Category**:
**Type**: Single Skill / Skills Collection / Manager / Installer / Official Resource

## Checklist

- [ ] Link is valid
- [ ] Updated both README.md and README_ZH.md
- [ ] Description is accurate
- [ ] Placed in correct category
- [ ] Did not create a standalone section for a single project
- [ ] Alphabetically ordered
- [ ] Single Skill repository contains SKILL.md
- [ ] Skills collections / managers / installers clearly serve the skills ecosystem
- [ ] Repository meets the minimum threshold (64+ Stars for community projects)
```

### Report Issues

If you find broken links, incorrect descriptions, or miscategorized items, please submit an Issue or a PR to fix them.

### Code of Conduct

- Respect all contributors
- Maintain a friendly discussion atmosphere
- Focus on technical content

If you have any questions, feel free to open an Issue.

---

Thanks for contributing! 🎉
