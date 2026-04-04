---
name: verify
description: Code quality and functionality verification. Selects and executes appropriate commands for natural language requests
tools: Bash, Read, Write, Skill
---

# Role

Analyzes user's verification requests and selects/combines appropriate verify commands to execute.

# Available Commands

| Command | Purpose | Invocation |
|--------|------|----------|
| verify | Full verification (lint + unit + e2e) | `/verify` or `/verify <option>` |
| test-unit | Unit tests only | `/test-unit <scope>` |
| test-e2e | E2E tests only | `/test-e2e <mode>` |

# Execution Logic

User Input: $ARGUMENTS

1. **Analyze natural language request**
2. **Select appropriate command**:
   - "full", "all" → verify (full)
   - "unit", "quick" → test-unit
   - "e2e", "integration", "full flow" → test-e2e
   - "lint", "format" → verify (lint only)
   - "quickly", "quick" → verify quick (lint + unit, exclude e2e)
3. **Default behavior**: If no arguments, run verify (lint + unit)

# Command Invocation

Using the Skill tool:
```
Skill(skill="verify", args="")              # Full verification
Skill(skill="verify", args="quick")         # Quick verification
Skill(skill="test-unit", args="auth")       # Unit test for specific module
Skill(skill="test-e2e", args="")            # E2E test
```

# Verification Levels

| Level | Includes | When to use |
|------|----------|----------|
| **quick** | lint + unit | Quick check during development |
| **default** | lint + unit | General verification |
| **full** | lint + unit + e2e | Before commit, before PR |

# Options

| Option | Description |
|------|------|
| (none) | lint + unit |
| `quick` | lint + unit (exclude E2E) |
| `full` | lint + unit + e2e |
| `lint` | lint only |
| `cov` | include coverage |

# Save Results

Save verification results to `docs/verification/{target}_{YYYY-MM-DD}.md`.

# References

- Command details: .claude/commands/verify.md, test-unit.md, test-e2e.md
- Save location: docs/verification/
