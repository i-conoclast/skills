---
name: verify
description: 코드 품질 및 기능 검증. 자연어 요청 시 적절한 커맨드를 선택하여 실행
tools: Bash, Read, Write, Skill
---

# 역할

사용자의 검증 요청을 분석하여 적절한 verify 커맨드를 선택/조합하여 실행한다.

# 사용 가능한 커맨드

| 커맨드 | 용도 | 호출 방법 |
|--------|------|----------|
| verify | 전체 검증 (lint + unit + e2e) | `/verify` 또는 `/verify <옵션>` |
| test-unit | 유닛 테스트만 | `/test-unit <범위>` |
| test-e2e | E2E 테스트만 | `/test-e2e <모드>` |

# 실행 로직

사용자 입력: $ARGUMENTS

1. **자연어 요청 분석**
2. **적절한 커맨드 선택**:
   - "전체", "full", "모든" → verify (full)
   - "유닛", "unit", "빠른" → test-unit
   - "e2e", "통합", "전체 흐름" → test-e2e
   - "린트", "lint", "포맷" → verify (lint만)
   - "빠르게", "quick" → verify quick (lint + unit, e2e 제외)
3. **기본 동작**: 인자 없으면 verify (lint + unit)

# 커맨드 호출 방법

Skill tool 사용:
```
Skill(skill="verify", args="")              # 전체 검증
Skill(skill="verify", args="quick")         # 빠른 검증
Skill(skill="test-unit", args="auth")       # 특정 모듈 유닛 테스트
Skill(skill="test-e2e", args="")            # E2E 테스트
```

# 검증 레벨

| 레벨 | 포함 항목 | 사용 시점 |
|------|----------|----------|
| **quick** | lint + unit | 개발 중 빠른 확인 |
| **default** | lint + unit | 일반적인 검증 |
| **full** | lint + unit + e2e | 커밋 전, PR 전 |

# 옵션

| 옵션 | 설명 |
|------|------|
| (없음) | lint + unit |
| `quick` | lint + unit (E2E 제외) |
| `full` | lint + unit + e2e |
| `lint` | 린트만 |
| `cov` | 커버리지 포함 |

# 결과 저장

검증 완료 후 결과를 `docs/verification/{target}_{YYYY-MM-DD}.md`에 저장한다.

# 참조

- 커맨드 상세: .claude/commands/verify.md, test-unit.md, test-e2e.md
- 저장 위치: docs/verification/
