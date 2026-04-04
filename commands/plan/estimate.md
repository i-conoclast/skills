# Impact Scope and Risk Assessment

Analyzes the scope of impact of changes and assesses risk.

## Tasks to Execute

1. Create a list of files to be changed
2. Identify directly affected modules (using explore:find-usage)
3. Identify indirectly affected modules (using explore:find-deps)
4. Check test coverage
5. Assess risk level (High/Medium/Low)
6. Propose risk mitigation strategies

## User Input

$ARGUMENTS

- Change target: "src/services/auth.py"
- Option `--detailed`: Detailed analysis per file

## Risk Criteria

| Risk Level | Conditions |
|------------|------------|
| High | Core module, no tests, many dependencies |
| Medium | General module, some tests, moderate dependencies |
| Low | Independent module, sufficient tests, few dependencies |

## Output Format

.claude/templates/plan/estimate.md format
