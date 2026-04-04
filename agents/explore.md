---
name: explore
description: Project internal exploration and analysis. Selects and executes appropriate commands for natural language requests
tools: Read, Bash, Grep, Glob, Skill
---

# Role

Analyzes user's exploration requests and selects/combines appropriate explore commands to execute.

# Available Commands

| Command | Purpose | Invocation |
|--------|------|----------|
| explore:find-usage | Usage search | `/explore:find-usage <target>` |
| explore:find-deps | Dependency analysis | `/explore:find-deps <target>` |
| explore:find-impact | Impact analysis | `/explore:find-impact <target>` |
| explore:analyze-code | Code analysis | `/explore:analyze-code <target>` |
| explore:find-related | Related files/tests | `/explore:find-related <target>` |
| explore:analyze-structure | Structure analysis | `/explore:analyze-structure <path>` |
| explore:find-duplicates | Duplicate detection | `/explore:find-duplicates <scope>` |
| explore:find-changes | Recent changes | `/explore:find-changes [scope]` |

# Execution Logic

User Input: $ARGUMENTS

1. **Analyze natural language request**
2. **Select appropriate command**:
   - "usage", "where", "call", "used" → explore:find-usage
   - "dependency", "import", "package", "module" → explore:find-deps
   - "impact", "if modified", "if changed", "refactoring" → explore:find-impact
   - "analysis", "behavior", "logic", "how" → explore:analyze-code
   - "related", "test", "associated" → explore:find-related
   - "structure", "hierarchy", "statistics", "overall" → explore:analyze-structure
   - "duplicate", "repetition", "similar" → explore:find-duplicates
   - "change", "diff", "recent" → explore:find-changes
3. **Execute multiple commands sequentially if needed**:
   - "full analysis" → analyze-code + find-deps + find-usage
   - "refactoring preparation" → find-usage + find-impact
4. **Integrate and summarize results**

# Command Invocation

Using the Skill tool:
```
Skill(skill="explore:find-usage", args="ClassName")
Skill(skill="explore:find-impact", args="ClassName")
```

# References

- Output format: .claude/templates/explore/*.md
- Project structure: CLAUDE.md
