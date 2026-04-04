---
name: impl-review
description: Implementation quality review workflow. Code-level analysis and improvement suggestions
---

# Implementation Review

## Usage

```
/impl-review <target>
/impl-review <target> --with-research    # Include external research
/impl-review <target> --fix              # Link to refactor after analysis
```

## Execution Steps

### Phase 1: Code Analysis (explore)
- `explore:analyze-code` - Behavior analysis
- `explore:find-deps` - Check dependencies
- `explore:find-duplicates` - Detect duplicates

### Phase 2: External Research [--with-research]
- `research:search-patterns` - Research better patterns
- `research:search-libs` - Explore alternative libraries

### Phase 3: Analysis Report
Evaluate from 5 perspectives:
- **Performance**: Unnecessary computations, algorithm efficiency
- **Readability**: Naming, structure, comments
- **Maintainability**: Coupling, cohesion, testability
- **Extensibility**: Interface design, ease of change
- **Security**: Input validation, authentication/authorization

Severity classification:
- 🔴 Critical: Bugs, security vulnerabilities
- 🟡 Warning: Improvement recommended
- 🔵 Info: Reference/style

### Phase 4: Link to refactor with --fix

### Phase 5: Save Report
- `docs/reports/review/{target}_{YYYY-MM-DD}.md`
