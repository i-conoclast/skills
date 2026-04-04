---
name: review-perspectives
description: Code review perspectives and severity criteria
---

# Review Perspectives

## 5 Evaluation Perspectives

### 1. Performance
- Unnecessary iterations/computations
- Algorithm time complexity
- Memory usage patterns
- I/O efficiency

### 2. Readability
- Variable/function naming
- Function size (30 lines or less recommended)
- Code structuring
- Appropriate abstraction level

### 3. Maintainability
- Coupling (lower is better)
- Cohesion (higher is better)
- Testability
- Documentation

### 4. Extensibility
- OCP (Open-Closed Principle) compliance
- Interface design
- Configurability

### 5. Security
- Input validation
- Authentication/authorization
- Sensitive data handling
- Dependency vulnerabilities

## Severity Criteria

| Severity | Description | Examples |
|----------|-------------|----------|
| 🔴 Critical | Immediate fix required | Bugs, security vulnerabilities, data loss risk |
| 🟡 Warning | Improvement recommended | Performance issues, code duplication, excessive complexity |
| 🔵 Info | For reference | Style, naming suggestions, documentation |

## structure-check vs impl-review Differences

| Item | structure-check | impl-review |
|------|----------------|-------------|
| Analysis level | Structural (files/modules) | Code-level (functions/logic) |
| Focus | Size, complexity, dependencies | Quality, patterns, security |
| Tools | Metric-based | Code review-based |
