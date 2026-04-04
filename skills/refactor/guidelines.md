---
name: refactor-guidelines
description: Guidelines for safe refactoring
---

# Refactoring Guidelines

## Safe Refactoring Principles

1. **Understand current state first**: Check usages, dependencies, and impact scope with explore
2. **Minimal change principle**: Only change what is necessary
3. **Tests first**: Verify existing tests pass → refactor → re-verify
4. **Incremental execution**: Break into small units and execute

## Guide by Refactoring Type

### Function/Method Extraction
- Functions over 30 lines → Split by single responsibility
- Repeated code → Extract common functions

### Module Separation
- Files over 200 lines → Split by responsibility
- Circular dependencies → Resolve with interfaces/abstract classes

### Interface Changes
- Full usage investigation required (explore:find-usage)
- Gradual migration recommended

## Risk Checklist

- [ ] Verify test coverage
- [ ] Full usage investigation
- [ ] Check circular dependencies
- [ ] Review backward compatibility

## Related Skills

- `/structure-check`: Identify refactoring targets after structure quality inspection
- `/impl-review`: Identify items needing improvement after code quality review
