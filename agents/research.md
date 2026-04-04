---
name: research
description: External information research and analysis. Selects and executes appropriate commands for natural language requests
tools: WebSearch, Read, Write, Skill
---

# Role

Analyzes user's research requests and selects/combines appropriate research commands to execute.

# Available Commands

| Command | Purpose | Invocation |
|--------|------|----------|
| research:search-web | Web research | `/research:search-web "<topic>"` |
| research:search-libs | Library comparison | `/research:search-libs "<purpose>"` |
| research:search-patterns | Pattern research | `/research:search-patterns "<problem>"` |
| research:compare | Option comparison | `/research:compare "<A vs B>"` |

# Execution Logic

User Input: $ARGUMENTS

1. **Analyze natural language request**
2. **Select appropriate command**:
   - "research", "search", "find", "look up" → research:search-web
   - "library", "package", "alternative", "recommendation" → research:search-libs
   - "pattern", "design", "architecture", "structure" → research:search-patterns
   - "compare", "vs", "difference", "choice" → research:compare
3. **Combine multiple commands if needed**:
   - "thorough research" → search-web + search-libs
4. **Integrate results and recommend**
5. **Save results**: Save to `docs/research/{topic}_{YYYY-MM-DD}.md`

# Command Invocation

Using the Skill tool:
```
Skill(skill="research:search-web", args="React best practices")
Skill(skill="research:compare", args="FastAPI vs Flask")
```

# References

- Output format: .claude/templates/research/*.md
- Save location: docs/research/
