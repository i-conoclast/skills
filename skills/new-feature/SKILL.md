---
name: new-feature
description: Full workflow for adding new features. explore → spec → research → plan → impl → verify
---

# New Feature Addition Workflow

## Usage

```
/new-feature <feature description>
/new-feature <feature description> --with-spec
/new-feature <feature description> --with-research
/new-feature <feature description> --full
```

## Execution Steps

### Step 1: Explore
- Spawn explore Agent:
  - `explore:analyze-structure` - Understand related directory structure
  - `explore:find-related` - Search for similar features/files
  - `explore:analyze-code` - Analyze existing patterns

### Step 2: Requirements Definition (spec) [--with-spec, --full]
- Spawn spec Agent:
  - `spec:define-fr` - Functional requirements
  - `spec:define-criteria` - Success criteria
  - `spec:define-scenarios` - Test scenarios
- **Approval gate**: Proceed after user confirmation

### Step 3: Research [--with-research, --full]
- Spawn research Agent:
  - `research:search-libs` - Related libraries
  - `research:search-patterns` - Applicable patterns
  - `research:compare` - Compare options (if needed)

### Step 4: Plan
- Spawn plan Agent:
  - `plan:design` - Design
  - `plan:breakdown` - Task decomposition
  - `plan:estimate` - Risk assessment
  - `plan:files` - File list
- **Approval gate**: Proceed after user confirmation

### Step 5: Implement (impl)
- Spawn impl Agent:
  - `impl:create` / `impl:modify` - Code implementation
  - `impl:test` - Write tests

### Step 6: Verify
- Spawn verify Agent:
  - lint + unit test + e2e test

### Step 7: Save Report
- `docs/reports/new-feature/{feature}_{YYYY-MM-DD}.md`

## Execution Modes

| Mode | Steps | Trigger |
|------|-------|---------|
| basic | explore → plan → impl → verify | Default |
| --with-spec | + spec | When requirements definition is needed |
| --with-research | + research | When technical research is needed |
| --full | All 7 steps | Complex features |
