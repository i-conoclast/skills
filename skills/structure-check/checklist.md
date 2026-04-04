---
name: structure-check-checklist
description: Structure quality evaluation criteria and metrics
---

# Quality Evaluation Criteria

## Metric Thresholds

| Metric | Warning 🟡 | Critical 🔴 |
|--------|-----------|-------------|
| File line count | > 200 | > 300 |
| Cyclomatic complexity | > 10 | > 15 |
| Function line count | > 30 | > 50 |
| Parameter count | > 3 | > 5 |
| Circular dependencies | Detected | - |
| Code duplication | > 80% | - |

## Inspection Commands

1. `explore:analyze-structure` - File statistics and structure
2. `explore:find-duplicates` - Duplicate code
3. `explore:find-deps` - Dependency graph

## Severity Classification

### 🔴 Critical
- Circular dependencies
- Files exceeding 300 lines
- Cyclomatic complexity exceeding 15

### 🟡 Warning
- Files with 200-300 lines
- Cyclomatic complexity 10-15
- 80%+ similar code

### 🔵 Info
- Empty __init__.py
- Unused imports
- Naming convention inconsistencies

## Recommended Inspection Frequency

| Timing | Scope |
|--------|-------|
| After adding features | Changed directories |
| Before PR | All changed files |
| Weekly | Entire project |
