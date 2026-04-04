---
name: structure-check
description: Code structure quality inspection. Analysis using explore command combinations
---

# Structure Quality Inspection

## Usage

```
/structure-check <scope>
/structure-check <scope> --fix    # Link to refactor after analysis
```

## Execution Steps

### Step 1: Structure Analysis
- `explore:analyze-structure` - File statistics, hierarchy structure

### Step 2: Duplicate Detection
- `explore:find-duplicates` - Detect duplicate/similar code

### Step 3: Dependency Analysis
- `explore:find-deps` - Check circular dependencies, coupling

### Step 4: Issue Classification
Classify each issue by category:
- **File size**: Warning for 200+ lines, critical for 300+ lines
- **Function complexity**: Warning for cyclomatic complexity 10+, critical for 15+
- **Circular dependencies**: Critical when detected
- **Code duplication**: 80%+ similarity
- **Single responsibility violation**: Mixed roles within a file

### Step 5: Severity Classification
- 🔴 Critical: Immediate fix required
- 🟡 Warning: Improvement recommended
- 🔵 Info: For reference

### Step 6: Link to refactor with --fix
- Run `/refactor` for critical issues

### Step 7: Save Report
- `docs/reports/structure-check/{target}_{YYYY-MM-DD}.md`
