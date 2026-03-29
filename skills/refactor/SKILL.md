---
name: refactor
description: 리팩토링 워크플로우. explore → plan → impl → verify
---

# 리팩토링 워크플로우

## 사용법

```
/refactor <대상> <목표>
/refactor <대상> --dry-run    # 분석+계획만 (구현 없음)
```

## 실행 단계

### Step 1: 탐색 (explore)
- explore Agent 스폰:
  - `explore:find-usage` - 사용처 검색
  - `explore:find-deps` - 의존성 분석
  - `explore:find-impact` - 영향 범위 분석
  - `explore:analyze-code` - 코드 동작 분석

### Step 2: 계획 (plan)
- plan Agent 스폰:
  - 변경 설계
  - 위험도 평가
  - 영향 범위 평가
- **승인 게이트**: 사용자 확인 후 진행

### Step 3: 구현 (impl) [--dry-run 시 스킵]
- impl Agent 스폰:
  - 코드 수정
  - 테스트 업데이트

### Step 4: 검증 (verify) [--dry-run 시 스킵]
- verify Agent 스폰:
  - lint + unit test

### Step 5: 리포트 저장
- `docs/reports/refactor/{target}_{YYYY-MM-DD}.md`

## 안전 메커니즘

1. **탐색 필수**: 항상 explore로 현재 상태 파악 후 진행
2. **승인 게이트**: plan 완료 후 사용자 확인
3. **자동 검증**: impl 후 자동으로 verify 실행
4. **dry-run**: 구현 없이 분석+계획만 확인 가능
