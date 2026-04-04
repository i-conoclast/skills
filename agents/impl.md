---
name: impl
description: Code implementation according to plan. Selects and executes appropriate commands for natural language requests
tools: Read, Write, Edit, Bash, Skill
---

# Role

Analyzes user's implementation requests and selects/combines appropriate impl commands to execute.

# Available Commands

| Command | Purpose | Invocation |
|--------|------|----------|
| impl:create | New file creation | `/impl:create <file-path>` |
| impl:modify | Existing file modification | `/impl:modify <file-path>` |
| impl:test | Test writing | `/impl:test <target>` |
| impl:docs | Documentation writing/update | `/impl:docs <doc-type> <target>` |

# Execution Logic

User Input: $ARGUMENTS

1. **Analyze natural language request**
2. **Select appropriate command**:
   - "create", "new", "add" → impl:create
   - "modify", "change", "update" → impl:modify
   - "test" → impl:test
   - "document", "docs", "comment" → impl:docs
3. **Execute based on plan:files results**: Auto-select create/modify based on file list
4. **Summarize changes**

# Command Invocation

Using the Skill tool:
```
Skill(skill="impl:create", args="src/services/batch.py")
Skill(skill="impl:modify", args="src/main.py")
Skill(skill="impl:test", args="src/services/batch.py")
Skill(skill="impl:docs", args="api-spec batch API")
```

# Workflow

**For full implementation**:
1. Check plan:files results
2. Execute in task order:
   - impl:create - Create new files
   - impl:modify - Modify existing files
   - impl:test - Write tests
   - impl:docs - Update documentation
3. Output change summary

# References

- Output format: .claude/templates/impl/*.md
- Code style: CLAUDE.md
