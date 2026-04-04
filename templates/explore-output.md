# Explore Output Format

## find-usage Output

### `{target}` Usage Locations

| # | File | Line | Context |
|---|------|------|---------|
| 1 | `src/...` | L42 | Call/import/reference description |

**Summary**: Used in N files, M locations total

---

## find-deps Output

### `{target}` Dependencies

**Internal Dependencies** (imported by this file):
| Module | Purpose |
|--------|---------|
| `src.models.user` | User model |

**Reverse Dependencies** (files that import this file):
| Module | Purpose |
|--------|---------|
| `src.routers.auth` | Authentication handling |

**External Packages**:
| Package | Version | Purpose |
|---------|---------|---------|

**Dependency Graph**:
```
A -> B -> C
       -> D
```

---

## find-impact Output

### `{target}` Change Impact

**Direct Impact** (1-depth):
| File | Impact Description |
|------|--------------------|

**Indirect Impact** (2-depth):
| File | Path | Impact Description |
|------|------|--------------------|

**Related Tests**:
| Test File | Number of Related Tests |
|-----------|------------------------|

**Risk Level**: 🟢 Low / 🟡 Medium / 🔴 High

---

## find-related Output

### `{target}` Related Files

**Source Files**: Files in the same module/directory
**Test Files**: Related tests
**Documentation Files**: Related documentation

---

## analyze-structure Output

### `{path}` Structure Analysis

**File Statistics**:
| Item | Value |
|------|-------|
| Number of Files | N |
| Total Lines | N |
| Average Lines | N |

**Directory Structure**:
```
path/
├── file1.py (N lines)
├── file2.py (N lines)
└── sub/
    └── file3.py (N lines)
```

**Key Classes/Functions**:
| Name | File | Lines | Description |
|------|------|-------|-------------|

---

## analyze-code Output

### `{target}` Code Analysis

**Overview**: One-line description of the file/function's role

**Core Logic**:
1. Step 1 description
2. Step 2 description

**Dependencies**: Key import list
**Notable Points**: Points to be aware of

---

## find-duplicates Output

### Duplicate Code Detection Results

| # | File A | File B | Similarity | Lines |
|---|--------|--------|------------|-------|

**Extraction Recommended**:
- Common logic description -> Suggested extraction location

---

## find-changes Output

### Recent Changes

| File | Status | Lines Changed | Key Changes |
|------|--------|---------------|-------------|

**Summary**: N files changed, +A/-B lines
