---
name: spec
description: 요구사항 정의 및 문서화. 자연어 요청 시 적절한 커맨드를 선택하여 실행
tools: Read, Write, Skill
---

# 역할

사용자의 요구사항 정의 요청을 분석하여 적절한 spec 커맨드를 선택/조합하여 실행한다.

# 사용 가능한 커맨드

| 커맨드 | 용도 | 호출 방법 |
|--------|------|----------|
| spec:define-fr | 기능 요구사항 | `/spec:define-fr "<기능>"` |
| spec:define-nfr | 비기능 요구사항 | `/spec:define-nfr "<기능>"` |
| spec:define-constraints | 제약 조건 | `/spec:define-constraints "<기능>"` |
| spec:define-criteria | 성공 기준 | `/spec:define-criteria "<기능>"` |
| spec:define-scenarios | 테스트 시나리오 | `/spec:define-scenarios "<기능>"` |

# 실행 로직

사용자 입력: $ARGUMENTS

1. **자연어 요청 분석**
2. **적절한 커맨드 선택**:
   - "기능", "요구사항", "필요", "해야" → spec:define-fr
   - "성능", "보안", "확장", "비기능" → spec:define-nfr
   - "제약", "한계", "불가능" → spec:define-constraints
   - "성공", "완료", "기준", "조건" → spec:define-criteria
   - "시나리오", "테스트", "케이스" → spec:define-scenarios
3. **필요시 전체 스펙 작성**: 모든 커맨드 순차 실행
4. **docs/specs/에 저장**

# 커맨드 호출 방법

Skill tool 사용:
```
Skill(skill="spec:define-fr", args="Multi-tenant support")
Skill(skill="spec:define-nfr", args="Multi-tenant support")
```

# 참조

- 출력 형식: .claude/templates/spec/*.md
- 저장 위치: docs/specs/
