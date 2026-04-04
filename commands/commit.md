# Create Git Commit

Generates a commit message and commits following Conventional Commits rules.

## Commit Types

| Type | Description | Example |
|------|-------------|---------|
| `feat` | New feature | feat: add user authentication |
| `fix` | Bug fix | fix: resolve timeout handling |
| `refactor` | Refactoring | refactor: extract service layer |
| `docs` | Documentation | docs: update API documentation |
| `test` | Tests | test: add unit tests for auth |
| `chore` | Build/config | chore: update lint config |
| `perf` | Performance improvement | perf: add caching layer |

## Tasks to Execute

1. Check changes with `git status`
2. Analyze changes and determine appropriate commit type
3. Generate commit message
4. Execute commit after user confirmation

## User Input

$ARGUMENTS

- No arguments: Suggest commit message after analyzing changes
- Specify type: Directly specify in `feat: description` format
- `--amend`: Amend the last commit

## Message Format

```
<type>: <subject>

[optional body]

[optional footer]
```

### Subject Rules
- 50 characters or less
- Start with a present tense verb
- No period at the end
