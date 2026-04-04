---
name: debugging
description: Systematic debugging workflow and error analysis patterns
---

# Debugging Workflow

## Triggers

- `/debug <error description>` or when debugging is requested in natural language
- When analysis is requested after test failure

## Workflow

### Step 1: Error Analysis
- Parse error messages/stack traces
- Identify related files and lines

### Step 2: Code Tracing
- Using explore Agent:
  - `explore:analyze-code` - Analyze code at failure point
  - `explore:find-deps` - Check related dependencies
  - `explore:find-impact` - Determine impact scope

### Step 3: Impact Analysis
- Directly affected files
- Related test files
- Configuration file check

### Step 4: Fix and Verify
- Suggest fix code
- Run verification with verify Agent

## Automatic Hook Integration

Automatic analysis on test failure:
- Identify failed test files
- Classify error patterns (assertion, import, runtime, timeout)
- Automatically search related code

## Error Pattern Classification

| Pattern | Keywords | Action |
|---------|----------|--------|
| Import error | ImportError, ModuleNotFound | Check dependencies |
| Type error | TypeError, AttributeError | Check interface |
| Runtime error | RuntimeError, ValueError | Analyze logic |
| Test failure | AssertionError | Compare expected vs actual values |
| Timeout | TimeoutError | Check performance/infinite loops |
