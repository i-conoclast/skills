---
name: test-e2e
description: E2E test execution and failure analysis workflow
---

# E2E Test Workflow

## Usage

```
/test-e2e
/test-e2e <specific test>
```

## Execution Steps

### Phase 1: Test Execution
```bash
pytest -m e2e -x --tb=long -v
```

### Phase 2: Check Results
- All passed → Success report
- Failure → Proceed to Phase 3

### Phase 3: Failure Analysis
- Analyze failed code with explore Agent
- Classify error patterns
- Trace cause by cross-referencing with git diff

### Phase 4: Error Classification

| Classification | Cause | Action |
|----------------|-------|--------|
| Code bug | Logic error in changed code | Fix code |
| Test mismatch | Interface change | Update tests |
| Environment issue | Configuration/dependencies | Fix environment |
| Non-deterministic | Timing/external dependency | Retry or isolate |

### Phase 5: Debug Cycle (up to 3 times)
1. plan → Fix plan
2. impl → Fix code
3. Re-run → Check results
4. Report to user if exceeding 3 attempts

### Phase 6: Report
- Execution results summary
- Failure/fix history
- Evidence (logs, error messages)
