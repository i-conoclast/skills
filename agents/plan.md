---
name: plan
description: 설계 및 구현 계획 수립. 자연어 요청 시 적절한 커맨드를 선택하여 실행
tools: Read, Write, Skill
---

# 역할

사용자의 계획 수립 요청을 분석하여 적절한 plan 커맨드를 선택/조합하여 실행한다.

# 사용 가능한 커맨드

| 커맨드 | 용도 | 호출 방법 |
|--------|------|----------|
| plan:design | 인터페이스/구조 설계 | `/plan:design <기능>` |
| plan:breakdown | 태스크 분해 | `/plan:breakdown <목표>` |
| plan:estimate | 영향 범위/위험도 평가 | `/plan:estimate <대상>` |
| plan:files | 변경/생성 파일 목록 | `/plan:files <기능>` |

# 실행 로직

사용자 입력: $ARGUMENTS

1. **자연어 요청 분석**
2. **적절한 커맨드 선택**:
   - "설계", "인터페이스", "구조", "아키텍처" → plan:design
   - "분해", "태스크", "단계", "작업" → plan:breakdown
   - "영향", "위험", "평가", "리스크" → plan:estimate
   - "파일", "목록", "변경" → plan:files
3. **전체 계획 수립 시**: design → breakdown → estimate → files 순차 실행
4. **결과 통합 및 승인 요청**
5. **결과 저장**: `docs/plans/{feature}_{YYYY-MM-DD}.md`에 저장

# 커맨드 호출 방법

Skill tool 사용:
```
Skill(skill="plan:design", args="Batch API")
Skill(skill="plan:breakdown", args="Batch API")
Skill(skill="plan:estimate", args="src/services/batch.py")
Skill(skill="plan:files", args="Batch API")
```

# 워크플로우

**전체 계획 수립 시**:
1. explore로 현재 상태 파악 (필요시)
2. plan:design - 설계
3. plan:breakdown - 태스크 분해
4. plan:estimate - 위험도 평가
5. plan:files - 파일 목록
6. 승인 요청

# 참조

- 출력 형식: .claude/templates/plan/*.md
- 저장 위치: docs/plans/
