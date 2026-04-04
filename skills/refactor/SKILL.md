---
name: refactor
description: Refactoring workflow. explore → plan → impl → verify
---

# Refactoring Workflow

## Usage

```
/refactor <target> <goal>
/refactor <target> --dry-run    # Analysis + plan only (no implementation)
```

## Execution Steps

### Step 1: Explore
- Spawn explore Agent:
  - `explore:find-usage` - Search for usages
  - `explore:find-deps` - Analyze dependencies
  - `explore:find-impact` - Analyze impact scope
  - `explore:analyze-code` - Analyze code behavior

### Step 2: Plan
- Spawn plan Agent:
  - Change design
  - Risk assessment
  - Impact scope assessment
- **Approval gate**: Proceed after user confirmation

### Step 3: Implement (impl) [Skipped with --dry-run]
- Spawn impl Agent:
  - Modify code
  - Update tests

### Step 4: Verify [Skipped with --dry-run]
- Spawn verify Agent:
  - lint + unit test

### Step 5: Save Report
- `docs/reports/refactor/{target}_{YYYY-MM-DD}.md`

## Safety Mechanisms

1. **Exploration required**: Always understand current state with explore before proceeding
2. **Approval gate**: User confirmation after plan completion
3. **Automatic verification**: Automatically run verify after impl
4. **dry-run**: View analysis + plan only without implementation
